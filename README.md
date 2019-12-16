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
	  
	Вкладки формы:
	[{"caption":"Image", "fields": [
	    {"field":"title","caption":"Заголовок"},
	    {"field":"description","caption":"Описание","inputTVtype":"richtext"}, 
	    {"field":"color","caption":"Цвет","inputTVtype":"colorpicker" },
	    {"field":"image","caption":"Изображение","inputTVtype":"image"}
	  ]
	}]
	
	Разметка колонок:
	[{
	  "header": "Заголовок", "sortable": "true", "dataIndex": "title"
	},{
	  "header": "Описание", "sortable": "true", "dataIndex": "description"
	},{
	  "header": "Цвет", "sortable": "true", "dataIndex": "color"
	},{
	  "header": "Изображение", "sortable": "false", "dataIndex": "image","renderer": "this.renderImage"
	}]
	  
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
	  
	  <a href="[[~[[+id]]]]">[[+pagetitle]]</a>
 
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
	[[if? &is=`[[+tv.product-table-second]]:empty` &then=`` &else=``]]
	[[*myMigxVariable:empty=`do this`:notempty=`do that`]]
	
	[[getImageList?
	    &tvname=`general-characteristics`
	    &tpl=`general-characteristics`
	    &toPlaceholder=`myMigxPh`
	]]
	[[+myMigxPh:isnot=``:then=`
	    <h4 class="text-upper">Общие Характеристики</h4>
	    <div class="description-table">
		[[+myMigxPh]]
	    </div>
	`:else=``]]


# pdoResources
                <div id="products-wrap" class="row">

                    [[!pdoPage?
                        &parents=`[[*id]]`
                        &tpl=`price-item-full`
                        &includeContent=`1`
                        &hideContainers=`1`
                        &tvPrefix=`tv.`
                        &includeTVs=`image,price,quantity`
                        &resources=`[[url-params-filter]]`
                        &sortdir=`ASC`
                        &limit=`9`
                        &tplPageWrapper=`@INLINE <nav aria-label="pagination"><ul class="pagination">[[+first]][[+prev]][[+pages]][[+next]][[+last]]</ul></nav>`
                        &tplPageFirst=`@INLINE <li class="page-item"><a class="page-link" href="[[+href]]">Первая</a></li>`
                        &tplPageLast=`@INLINE <li class="page-item"><a class="page-link" href="[[+href]]">Последняя</a></li>`
                        &tplPage=`@INLINE <li class="page-item"><a class="page-link" href="[[+href]]">[[+pageNo]]</a></li>`
                        &tplPageActive=`@INLINE <li class="page-item active"><a class="page-link" href="[[+href]]">[[+pageNo]]</a></li>`
                        &tplPagePrev=`@INLINE <li class="page-item"><a class="page-link" href="[[+href]]"><span aria-hidden="true">&laquo;</span><span class="sr-only">Previous</span></a></li>`
                        &tplPageNext=`@INLINE <li class="page-item"><a class="page-link" href="[[+href]]"><span aria-hidden="true">&raquo;</span><span class="sr-only">Next</span></a></li>`
                        &tplPagePrevEmpty=`@INLINE <li class="page-item disabled"><a class="page-link" href="[[+href]]"><span aria-hidden="true">&laquo;</span><span class="sr-only">Previous</span></a></li>`
                        &tplPageNextEmpty=`@INLINE <li class="page-item disabled"><a class="page-link" href="[[+href]]"><span aria-hidden="true">&raquo;</span><span class="sr-only">Next</span></a></li>`
                        &tplPageFirstEmpty=``
                        &tplPageLastEmpty=``
                    ]]
                    
                    <div class="col-sm-12 pagination pt-5">
                        <div class="mx-auto">
                            [[!+page.nav]]
                        </div>
                    </div>
                </div>



# pdoCrumbs
        <div class="row bread d-none d-sm-block">
            <nav aria-label="breadcrumb">
                [[pdoCrumbs?
                    &to=`[[*id]]`
                    &tpl=`@INLINE <li class="breadcrumb-item"><a href="[[+link]]">[[+menutitle]]</a></li>`
                    &tplCurrent=`@INLINE <li class="breadcrumb-item active"><a href="[[+link]]">[[+menutitle]]</a></li>`
                    &tplWrapper=`@INLINE <ol class="breadcrumb">[[+output]]</ol>`
                    &showCurrent=`1`
                    &showHome=`1`
                ]]
            </nav>
        </div>
