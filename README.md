# JQuery 頁籤效果

##HTML:

    <!--Blue style-->
    <div class="tab">
        <ul class="tabNav">
            <li><a href="#">選項1</a></li>`<br>
            <li><a href="#">選項2</a></li>
            <li><a href="#">選項3</a></li>
        </ul>
        <ul class="tabContainer">
            <li>內容1</li>
            <li>內容2</li>
            <li>內容3</li>
        </ul>
     </div><!--tab-->
	
	
    <!--Pink style-->
    <div class="tab pinkTab">
        <ul class="tabNav">
            <li><a href="#">選項1</a></li>
            <li><a href="#">選項2</a></li>
            <li><a href="#">選項3</a></li>
        </ul>    
        <ul class="tabContainer">
            <li>內容1</li>
            <li>內容2</li>
            <li>內容3</li>
        </ul>
    </div><!--tab-->`

##CSS:
	 ul{margin:0;padding:0; list-style-type:none;}
	.tab{ margin-bottom: 14px;}
	.tab .tabNav{ overflow:auto; background:#D6D6D6 ;}
	.tab .tabNav>li{ float: left; width: 33.3333333333%;}
	.tab .tabNav>li a{ display: block; padding: 10px 0; text-align: center;  }
	.tab .tabNav>li a:hover{ background: #bbb; }
	.tab .tabNav>li.active a{ background:#0C5EB2; color: #fff;}
	.tab a{text-decoration: none; color: inherit;}
	.tab .tabContainer{ overflow: auto;   }
	.tab .tabContainer>li{ width: 92%; min-height:180px; padding: 10px 4%; background: #efefef; }
	.pinkTab .tabNav>li.active a{ background:#E782B5;}
	
	
##JS:
	$(function(){
		
		$('.tabContainer>li').not(':first-child').hide();
		$('.tabNav>li:first-child').addClass('active');
		$('.tabNav a').click(function() {
			var $this = $(this),
				$tabContainer = $this.parents('.tabNav').siblings('.tabContainer'),
				$tabContainerLi	= $tabContainer.children('li'),
				_index = $this.parent().index();
			$this.parent().addClass('active').siblings().removeClass('active');
			$tabContainerLi.eq(_index).show().siblings().hide();
			return false;
		});
	});
	
