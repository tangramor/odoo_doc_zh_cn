# odoo_doc_zh_cn: odoo 文档中文翻译项目

$ pip install sphinx-patchqueue
$ pip install mercurial

Exception occurred:
  File "/Library/Python/2.7/site-packages/docutils/writers/html4css1/__init__.py", line 1129, in visit_list_item
    node[0]['classes'].append('first')
TypeError: string indices must be integers

Fix: vi /Library/Python/2.7/site-packages/docutils/writers/html4css1/__init__.py and go to line 1129, modify it to:

    def visit_list_item(self, node):
        self.body.append(self.starttag(node, 'li', ''))
        if len(node):
            #node[0]['classes'].append('first')
            node['classes'].append('first')
