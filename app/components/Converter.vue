<template>
    <Page>
        <ActionBar>
            <Label text="Converter"/>
        </ActionBar>
        <StackLayout>
            <Button @tap="$navigateBack">назад</Button>
            <Label :text="LabelText1"></Label>
            <TextField v-model="text1" :text="text1"/>    
            <Button @tap="change(1)">⇅</Button>
            <Label :text="LabelText2"></Label>
            <TextField v-model="text2" :text="text2"/>    
            <Button @tap="change(2)">⇅</Button>
            <Label :text="LabelText3"></Label>
            <TextField v-model="text3" :text="text3"/>    
            <Button @tap="convert(ConvertType)">конвертировать</Button>
        </StackLayout>
    </Page>
</template>

<script>

  export default {
    data () {
      return {
        a: ""
      };
    },
    
    props:{
      LabelText1:{
        type: String
      },
      LabelText2:{
        type: String
      },
      LabelText3:{
        type: String
      },
      text1:{
        type: Number
      },
      text2:{
        type: Number
      },
      text3:{
        type: Number
      },
      ConvertType:{
        type: Number
      },
    },
    
  
    methods: {
      convert(ConvertType) {
        if(ConvertType==1)
        {
          this.text2 = this.text1 * 0.001
          this.text3 = this.text1 * 0.0022046226
        }
        if(ConvertType==2)
        {
          this.text2 = this.text1 * 0.001
          this.text3 = this.text1 * 2.236936284
        }
        if(ConvertType==3)
        {
          this.text2 = this.text1 * 33.8
          this.text3 = this.text1 * 274.15
        }
        if(ConvertType==4)
        {
          this.text2 = this.text1 * 0.01
          this.text3 = this.text1 * 0.00001
        }
        if(ConvertType==5)
        {
          this.text2 = this.text1 * 0.000001
          this.text3 = this.text1 * 0.0002
        }

      },
      change(n){
        if(n==1)
        {
          this.a = this.text1
          this.text1 = this.text2
          this.text2 = this.a
        }
        else
        {
          this.a = this.text2
          this.text2 = this.text3
          this.text3 = this.a
        }
      }
    }
  };
</script>

<style scoped>
    Label {
        font-size: 24;
        text-align: left;
        background: #fff;
        color: #111;
        padding-left: 20;
    }
    Button {
        background-color: rgba(0, 162, 255, 0.521);
        margin: 0;
        border-radius: 1%;
        font-size: 25;
        margin: 20px;
    }
    .number {
        width: 33.3333333%;
    }
</style>