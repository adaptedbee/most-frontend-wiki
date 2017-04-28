## Кастомные чекбоксы

Описание

## HTML

```
<form class="form">
  <ul>
    <li>
      <input type="checkbox" id="checkbox1" name="checkbox1">
      <label for="checkbox1">Checkbox 1</label>
    </li>
    <li>
      <input type="checkbox" id="checkbox2" name="checkbox2">
      <label for="checkbox2">Checkbox 2</label>
    </li>
    <li>
      <input type="checkbox" id="checkbox3" name="checkbox3">
      <label for="checkbox3">Checkbox 3</label>
    </li>
  </ul>
  <button type="submit">Отправить</button>
</form>
```

## CSS

```
.form input[type="checkbox"] {
  display: none;
}
.form input[type="checkbox"] + label {
  position: relative;
  display: inline-block;
  padding-left: 40px;
  cursor: pointer;
  vertical-align: top;
}
.form input[type="checkbox"] + label:hover {
  color:#663d15;
}
.form input[type="checkbox"]:disabled + label {
  opacity: 0.4;
}
.form input[type="checkbox"] + label::before {
  content: "";
  position: absolute;
  width: 20px;
  height:20px;
  top: 2px;
  left: 0;
  background: url("../img/sprite.png") no-repeat;
}
.form input[type="checkbox"] + label::before {
  background-position: 0px 0px;
}
.form input[type="checkbox"]:checked + label::before {
  background-position: 0px -30px;
}
```