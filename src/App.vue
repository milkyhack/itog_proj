<template>
    <html lang="ru">
        <head>
            <meta charset="UTF-8">
            <meta name="viewport" content="width-device-width , initial-scale=1.0">
            <link rel="preconnect" href="https://fonts.googleapis.com">
            <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
            <link href="https://fonts.googleapis.com/css2?family=Noto+Serif:ital@1&display=swap" rel="stylesheet"> 
        </head>
        <body>
            <div class="header">
                <div class="container">
                    <div class="logo">Сегодня</div>
                    <div class="form">
                        <input type="text" v-bind:value='valueInput'>
                        <button class="btn">Добавить</button>
                    </div>
                </div>
            </div>
            <div class="container">
                 <h2>
                     <span>Сделать</span>
                     <span class="mask-num">10</span>
                 </h2>
                 <ul class="mask-list">
                     <li>
                         <div>
                             <input type="checkbox">
                             <span>хлеб</span>
                         </div>
                         <button class="btn-remove">убрать</button>
                     </li>
                 </ul>
                   <h2>
                     <span>Сделано</span>
                     <span class="mask-num">10</span>
                 </h2>
                 <ul class="mask-list complete-list">
                     <li>
                         <div>
                             <input type="checkbox" checked >
                             <span>хлеб</span>
                         </div>
                         <button class="btn-remove">убрать</button>
                     </li>
                 </ul>
            </div>
        </body>
    </html>
</template>

<script>
({
    data() {
        valueInput:'new'
},
methods:{

}
})
</script>

<style>
body {
  font-family: 'Noto Serif', serif;  
  font-weight: 300;
}

h2 {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding-bottom: 20px;
  margin: 25px 0;
  border-bottom: 1px solid #bfbfbf;
}

h2 .mask-num {
  border-radius: 20px;
  border: 2px solid #2a2f36;
  color: #2a2f36;
  font-size: 14px;
  font-weight: 700;
  padding: 5px 10px;
}

.container {
  width: 800px;
  margin: 0 auto;
  padding: 0 15px;
}

.header {
  background-color: rgb(13, 100, 57);
  padding: 10px 0;
  margin-bottom: 40px;
}

.header .container {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.header .container .logo {
  width: 100px;
  line-height: 50px;
  color: #ddd;
  font-size: 24px;
  cursor: pointer;
}

.header .container .form {
  width: 60%;
  display: flex;
  justify-content: space-between;
}

.header .container .form input {
  width: calc(100% - 145px);
  height: 40px;
  text-indent: 10px;
  border: 1px solid #fff;
  border-radius: 5px;
  border-radius: 15px;
  box-sizing: border-box;
  outline: none;
  transition: 0.2s border;
}

.header .container .form input:focus {
  border: 1px solid #12c0dd;
}

.btn {
  background-color: #14684f;
  border: 1px solid #12c0dd;
  border-radius: 15px;
  color: #fff;
  font-weight: 700;
  text-transform: uppercase;
  padding: 10px 15px;
  font-size: 12px;
  height: 40px;
  outline: none;
  transition: 0.2s;
}

.btn:hover {
  background-color: #0dd6f8;
  border-color: #0dd6f8;
}

.mask-list li {
  display: flex;
  align-items: center;
  justify-content: space-between;
  height: 32px;
  line-height: 32px;
  margin-bottom: 10px;
  border-radius: 3px;
  background-color: #fff;
}

.mask-list.complete-list li {
  border-left-color: #999;
  opacity: .5;
}
.mask-list {
    padding-left: 0;
}

input[type="checkbox"] + span {
    padding-left: 10px;
}

.btn-remove {
    border: 1px solid #2a2f36;
    border-radius: 15px;
    font-size: 12px;
    border: 2px solid #2a2f36;
    background-color: #333333;
    color: #fff;
    font-weight: 700;
    text-transform: uppercase;
    padding: 5px 10px;
    font-size: 12px;
    outline: none;
    transition: 0.2s;
}

.btn-remove:hover {
  background-color: #535151;
  border-color: #535151;
}

input[type="checkbox"]:checked,
input[type="checkbox"]:not(:checked){
   position: absolute;
   z-index: 1;
   opacity: 0;
   width: 20px;
   height: 20px;
   margin-top: 6px;
}
input[type="checkbox"]:checked + span,
input[type="checkbox"]:not(:checked) + span{
   position: relative;
   padding-left: 35px;
   cursor:pointer;
}
input[type="checkbox"]:checked + span::before{
   content:'';
   position: absolute;
   width: 16px;
   height: 16px;
   left:0;
   top:calc(50% - 10px);
   background-color: transparent;
   border-radius: 2px;
   border: 2px solid #4fc1de;
}
input[type="checkbox"]:checked + span::after{
   content:'';
   position: absolute;
   width: 12px;
   height: 12px;
   transition: all .2s ease;
   opacity: 1;
   left: 4px;
   top: calc(50% - 6px);
   background-color: #4fc1de;
}
input[type="checkbox"]:not(:checked) + span::before{
   content:'';
   position: absolute;
   width: 16px;
   height: 16px;
   left:0;
   top:calc(50% - 10px);
   background-color: transparent;
   border-radius: 2px;
   border: 2px solid #5d575f;
}
input[type="checkbox"]:not(:checked) + span::after{
   content:'';
   position: absolute;
   width: 12px;
   height: 12px;
   transition: all .2s ease;
   opacity: 0;
   left: 4px;
   top: calc(50% - 6px);
   background-color: #7d25a9;
}
</style>