<template>
    <Page>
        <ActionBar>
            <Label text="Converter"/>
        </ActionBar>
        <StackLayout >
          <Label>Выберите величину</Label>
          <Button @tap="goToWeight()">Масса</Button>
          <Button @tap="goToSpeed()">Скорость</Button>
          <Button @tap="goToTemp()">Температура</Button>
          <Button @tap="goToLength()">Длина</Button>
          <Button @tap="goToArea()">Площадь</Button>
        </StackLayout>
    </Page>
    
</template>


<script>

import Converter from './Converter'

  export default {
    data () {
      return {
        Converter: Converter,
      };
    },
    methods: {
    goToWeight() {
      this.$navigateTo(this.Converter, {    
          props:{
            LabelText1: "из: грамм",
            LabelText2: "в: килограмм",
            LabelText3: "в: фунт",
            ConvertType: 1
          }
      });
      
    },
    goToSpeed() {
      this.$navigateTo(this.Converter, {    
          props:{
            LabelText1: "из: м/с",
            LabelText2: "в: км/ч",
            LabelText3: "в: мл/ч",
            ConvertType: 2
          }
      });
      
    },
   
    goToTemp() {
      this.$navigateTo(this.Converter, {    
          props:{
            LabelText1: "из: цельсия",
            LabelText2: "в: фаренгейта",
            LabelText3: "в: кельвин",
            ConvertType: 3
          }
      });
      
    },
    goToLength() {
      this.$navigateTo(this.Converter, {    
          props:{
            LabelText1: "из: сантиметр",
            LabelText2: "в: метр",
            LabelText3: "в: километр",
            ConvertType: 4
          }
      });
      
    },
    goToArea() {
      this.$navigateTo(this.Converter, {    
          props:{
            LabelText1: "из: квадратный метр",
            LabelText2: "в: квадратный километр",
            LabelText3: "в: гектар",
            ConvertType: 5
          }
      });
      
    }
  },
}
  
</script>

<style scoped lang="scss">
button{
  background-color: rgb(67, 204, 204);
}
Label {
        font-size: 24;
        text-align: center;
        background: #fff;
        color: #111;
        padding-left: 20;
    }

</style>
