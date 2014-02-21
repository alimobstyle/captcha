# captcha

---

验证码

---

## 演示

### 默认

````html
<div class="ali-flexbox ali-captcha">
    <div class="ali-field ali-flexbox-item">
        <div class="ali-field-input">
            <input type="text" maxlength="4" placeholder="短信验证码">
        </div>
        <div class="ali-field-message">
            <div class="ali-field-message-arrow"></div>
            <p>提示信息</p>
        </div>
    </div>
    <div class="ali-captcha-button">
        <button type="button" disabled="disabled" class="ali-button ali-button-disabled">重获验证码</button>
    </div>
</div>
<div class="ali-flexbox ali-captcha">
    <div class="ali-field ali-field-error ali-flexbox-item">
        <div class="ali-field-input">
            <input type="text" maxlength="4" placeholder="短信验证码">
        </div>
        <div class="ali-field-message">
            <div class="ali-field-message-arrow"></div>
            <div class="ali-field-message-icon"></div>
            <p>提示信息</p>
        </div>
    </div>
    <div class="ali-captcha-button">
        <button type="button" disabled="disabled" class="ali-button ali-button-disabled">重获验证码</button>
    </div>
</div>
````

<script type="text/javascript">
window.addEventListener('load', function () {
    var interval = 500, begin = Date.now(), img = new Image(), timer = setTimeout(handler, interval);
    window.removeEventListener('load', arguments.callee);
    img.addEventListener('load', handler, false);
    img.src = 'https://i.alipayobjects.com/e/201305/Q9jNoeIir.gif?t=' + begin;

    function handler() {
        clearTimeout(timer);
        img.removeEventListener('load', handler);
        //响应在500ms以内算高速网络 高清（HD）标清（SD）
        document.body.className = (document.body.className + (Date.now() - begin < interval ? ' ali-hd' : ' ali-sd')).trim();
    }
}, false);
</script>
