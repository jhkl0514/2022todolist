<template>
<div class="contents">
  
    <!-- {{todoItem}} -->
    <ul>
        <li v-for="(item,i) in todoItem" :key="i" class="line">
        
        <div class="list">
            <div class="listWrap">
                <div class="btnDon"><img src="../assets/btn_chack.png" alt=""></div>
                <div class="conTxt"><span class="icon"></span>{{item}}</div>
                <div class="btnDel" @click="removeDel(i,item)"><img src="../assets/btn_del.png" alt=""></div>   
            </div>
                     
          
        </div>
        </li>   
    </ul>

                          
                    
</div>
</template>

<script>
export default {
    props:[
        "todoItem"
    ],
    //메소드스에서 자료를 보낸다.($emit) 속성값으로 처리 가능(함수들어올수 있음)
    methods:{
        removeDel(num,item){
            this.$emit("reDel",num,item)
            // num 어레이 ,item 로컬스토리지
        }
    }

}
</script>

<style lang="scss">
.contents {
  width: 320px;
  height: 380px;  
  background: #FFFFFF;
  box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.25);
  border-radius: 20px;
  margin-bottom: 10px;
  padding: 35px 12px; 

//   <div class="list">
//             <button class="btnDon"><img src="../assets/btn_chack.png" alt=""></button>
//             <div class="conTxt active"><span class="icon"></span>{{item}}</div>
//             <button class="btnDel" @click="removeDel(i,item)"><img src="../assets/btn_del.png" alt=""></button>            
          
//         </div>
    .line{
        display: flex; 
        justify-content:space-between;
        align-items: center;
        padding: 10px 15px;
        background: #F6F6F6;
        border-radius: 10px;
        font-size: 14px;
        line-height: 22px;
        letter-spacing: -0.03em;  
        color: #666;
        margin-bottom: 10px;
        .listWrap{
            display: flex;
              gap:10px;
              .btnDon{
                width: 30px;
                height: 30px;
                background: #032E53;
                border-radius: 50px;
                display: flex; justify-content: center; align-items: center; 
            }
            .conTxt{
                width: 200PX; 
                display: flex; align-items: center;
                font-weight: 600;               
                    .icon{
                    background-image: url(../assets/icon_01.png);
                    background-repeat: no-repeat;
                    width: 20px; height: 20px;
                    margin: 0 5px 0 10px;  
                    }  
                }   
             .btnDel{
                padding: 5px 20px 0 0;

                cursor: pointer;
                align-self: start;
                display: flex;
                justify-content: center;
                align-items: center;
                background: #F6F6F6;     
            }       
        }        
        
       
    }   

    
}


input[type='text']::placeholder,
textarea::placeholder{color:#bbb}
input:focus{outline: none;}
button{ border: 0 none;}

</style>