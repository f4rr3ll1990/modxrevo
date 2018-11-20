# urlOfPage
	[[~11? &scheme=`full`]]

# urlOfParent
	[[~[[*parent]]]]

# urlParam
	[[!getUrlParam? &name=`tag` &max=`999`]]
	<a href="[[~11? &scheme=`full`]]?tag=qwerty"></a>

# pdoMenu
	[[pdoMenu?  
		&level=`2` 
		&parents=`0`
		&outerClass=`nav navbar-nav`
		&tplOuter=`@INLINE <ul[[+classes]] id="menu">[[+wrapper]]</ul>` 
		&tplInner=`@INLINE <ul class="dropdown-menu">[[+wrapper]]</ul>` 
		&tplParentRow=`@INLINE  <li[[+classes]] dropdown>
                                      <a class="dropdown-toggle"[[+attributes]] data-hover="dropdown" data-delay="100" data-close-others="false" href="[[+link]]" [[+attributes]]>
                                        [[+menutitle]]<span class="caret"></span>
                                      </a>
                                      [[+wrapper]]
                                    </li>`
	]]
  
# getImageList
	  [[getImageList?
	    &tvname=`images`
	    &tpl=`images`
	  ]]
# MigX
	[{"caption":"Image", "fields": [
	    {"field":"title","caption":"Заголовок"},
	    {"field":"description","caption":"Описание","inputTVtype":"richtext"}, 
	    {"field":"color","caption":"Цвет","inputTVtype":"colorpicker" },
	    {"field":"image","caption":"Изображение","inputTVtype":"image"}
	  ]
	}]

	[{
	  "header": "Заголовок", "sortable": "true", "dataIndex": "title"
	},{
	  "header": "Описание", "sortable": "true", "dataIndex": "description"
	},{
	  "header": "Цвет", "sortable": "true", "dataIndex": "color"
	},{
	  "header": "Изображение", "sortable": "false", "dataIndex": "image","renderer": "this.renderImage"
	}]	  
	  
	  
  
# getResources
	  [[!getResources?
	      &parents=`[[~id]]`
	      &tpl=`item`
	      &showUnpublished=`0`
	      &showHidden=`1`
	      &limit=`0`
	      &includeTVs=`1`
	  ]]
 
# getResources(conditional tpl)
	[[!getResources?
	    &parents=`[[~id]]`
	    &sortby=`menuindex`
	    &tplCondition=`template`
	    &conditionalTpls=`{"4":"item","5":"item-reverse","6":"special", "7": "callback"}`
	    &tpl=`item`
	    &showUnpublished=`0`
	    &showHidden=`1`
	    &limit=`0`
	    &includeTVs=`1`
	    &includeContent=`1`
	]]

# getResourceField
	[[getResourceField? &id=`1` &field=`phone` &isTV=`1`]]

# AjaxForm
	  [[!AjaxForm?
	      &snippet=`FormIt`
	      &form=`form`
	      &emailTpl=`letter`
	      &hooks=`email`
	      &emailSubject=`Заказ звонка с сайта [[++site_url]]`
	      &emailTo=`admin@adm.com`
	      &validate=`name:required,tel:required`
	      &validationErrorMessage=`В форме содержатся ошибки!`
	      &successMessage=`<h3>Запрос отправлен!</h3>Наши специалисты свяжутся с<br>вами в ближайшее время.`
	  ]]

# IF
	[[!If? &subject=`[[+tv.sale]]` &operator=`EQ` &operand=`1` &then=`<p class="sticker">sale</p>`]]
