## Табы

Описание

## HTML

```
<div class="tabs">
  <ul class="tabs__menu js-tabs-menu">
    <li class="tabs__menu-item js-tabs-menu-item active">Tab 1</li>
    <li class="tabs__menu-item js-tabs-menu-item">Tab 2</li>
    <li class="tabs__menu-item js-tabs-menu-item">Tab 3</li>
  </ul>
  <div class='tabs__container js-tabs-container'>
    <div class="tabs__tab js-tab active">Tab Content 1</div>
    <div class="tabs__tab js-tab">Tab Content 2</div>
    <div class="tabs__tab js-tab">Tab Content 3</div>
  </div>
</div>
```

## CSS

```
.tabs{
  width: 780px;
  margin: 0 auto;
}

.tabs__menu{
  width: 100%;
  margin: 0 auto 50px;
  padding-left: 0;
  list-style: none;
  text-align: center;
}

.tabs__menu-item{
  display: inline-block;
  vertical-align: top;
  padding-left: 25px;
  padding-right: 25px;
  margin-right: 45px;

  cursor: pointer;

  transition: .2s;
}
.tabs__menu-item:last-child{
  margin-right: 0;
}

.tabs__tab{
  display: none;
}

.tabs__tab.active{
  display: block;
}
```

## JS

```
var tabsMenu = $('.js-tabs-menu');
var tabsContainer = $('.js-tabs-container');
var currentIndex;

tabsMenu.find('.js-tabs-menu-item').on('click', function(){
  $(this).parents('li').siblings().find('.active').removeClass('active');
  if (!$(this).hasClass('active')) $(this).addClass('active');

  currentIndex = $(this).parents('li').index();
  tabsContainer.find('.active').removeClass('active');
  tabsContainer.find('.js-tab').eq(currentIndex).addClass('active');
  }
});
```