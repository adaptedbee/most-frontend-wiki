## Хак для Magnific Popup

Работает, если все элементы попапа принадлежат блоку попапа (БЭМ).

## JS

```
$('.show-photos-popup').on('click', function() {
  $.magnificPopup.open({
    disableOn: false,
    items: {
      src: $('.photos-popup'),
      type: 'inline'
    },
    mainClass: 'mfp-fade',
    removalDelay: 160,
    preloader: false,
    fixedContentPos: true,
    fixedBgPos: true,
    callbacks: {
      open: function() {
        $('body').on('touchmove', function (e) {
          if (e.target.className.indexOf('photos-popup') === -1) {
            e.preventDefault();
          }
        });
        $('.photos-popup').removeClass('inactive');
      },
      close: function() {
        $('body').off('touchmove');
        $('.photos-popup').addClass('inactive');
      }
    }
  });
});
```