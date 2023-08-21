- > 这是一个首页，目前没有任何东西，后期会以各种维度通过 query 的方式将其他页面链接展示在这里。
- > 这是一个 query，作用是查询所有的标签
	- #+BEGIN_QUERY
	  {:title [:b "查询所有 tag"]
	   :query [:find ?ref-name
	           :where
	           (page-property ?p :public true)
	           [?b :block/parent ?p]
	           [?b :block/refs ?ref]
	           [?ref :block/name ?ref-name] 
	           ]
	   :view (fn [tags]
	      [:div
	       (for [tag (flatten tags)]
	         [:a.tag.mr-1 {:href (str "#/page/" tag)}
	          (str "#" tag)])])}
	   }
	  #+END_QUERY
-
- > 如果想参与编辑，请提交至这个[仓库](https://github.com/b-yp/A-Song-of-Ice-and-Fire)
- > 咨询请添加：QQ（1031984293）