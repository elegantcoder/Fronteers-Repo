In Field Labels 패턴
==================

## 문제
* 입력 필드 내에 캡션을 표시해야 함.
* 백그라운드 이미지로 글씨를 표시하는 경우 이미지 폰트여서 어색해 보이는 경우가 발생하기도 함

## 해결

### HTML
```html
	<div class="wrapper">
		<label for="example">비밀번호</label><input type="password" id="example">
	</div>
```

### CSS
```css
    .wrapper {
      position: relative;
      margin: 10px;
    }

    label{
      margin: 8px 0 0 4px;
    }

    input {
      position:absolute;
      left: 0;
      z-index:2;
      /* IE6~IE8 에서 배경이 투명한 input의 클릭 영역 문제 - 투명 gif 를 삽입해 해결 */
      background:transparent url('data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7') repeat left top;
    }

    input.focus {
      background-color: white;
    }
```

### JavaScript
```javascript
      (function ($) {
        var $input = $('#example');
        $input.on('click focus', function () {
          $input.css('background-color', 'white');
        }).on('blur', function () {
          if ($.trim($input.val()).length === 0) {
            $input.css('background-color', 'transparent');
          }
        });
      })(jQuery);
```

## 참고
* [입력 필드 내 텍스트 UI, 어떻게 구현하는 것이 좋을까?](http://elegantcoder.com/label-ui)