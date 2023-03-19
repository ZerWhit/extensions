let 变量名 = [];
let 变量的值 = [];
class 变量储存 {
    getInfo() {
        return {
            id: "fennd",
            name: "fennd的js变量",
            color1: "#ffab19",
            color2: "#ffab19",
            color3: "#ffab19",
            blocks: [{
                opcode: "放入",
                blockType: Scratch.BlockType.COMMAND,
                text: "放入变量[变量]数值[数值]",
                arguments: {
                    变量:{
                        type: Scratch.ArgumentType.STRING,
                        defaultValue: "var_name",
                    },
                    数值:{
                        type: Scratch.ArgumentType.STRING,
                        defaultValue: "data",
                    }
                },  
                },{
                opcode: "初始化",
                blockType: Scratch.BlockType.COMMAND,
                text: "将变量初始化",
                arguments: {},  
                },{
                    opcode: "寻找变量",
                    blockType: Scratch.BlockType.REPORTER,
                    text: "寻找变量[变量]",
                    arguments: {
                        变量:{
                            type: Scratch.ArgumentType.STRING,
                            defaultValue: "var_name",
                        },
                    },  
                    },{
                        opcode: "设置变量",
                        blockType: Scratch.BlockType.COMMAND,
                        text: "设置变量[变量]，赋值为[值]",
                        arguments: {
                            变量:{
                                type: Scratch.ArgumentType.STRING,
                                defaultValue: "var_name",
                            },
                            值:{
                                type: Scratch.ArgumentType.STRING,
                                defaultValue: "data",
                            },
                        },   
                    }],
        }

    }
    放入({
        变量,
        数值
    }){
        变量名.push(变量);
        变量的值.push(数值)
    }
    初始化({}){
        变量名 = [];
        变量的值 = [];
    }
    寻找变量({
        变量
    }){
        for (let i = 0; i < 变量名.length;i++){
            if (变量名[i] == 变量){
                return (变量的值[i])
            }
        }
        return ("没找到你存储的变量")
    }
    设置变量({
        变量,
        值
    }){
        for (let i = 0; i < 变量名.length;i++){
            if (变量名[i] == 变量){
                变量的值[i] = 值
            }
        }
    }

}
Scratch.extensions.register(new 变量储存());
