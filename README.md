# angular从0初学

> by 2018-08-29
* 主要创建项目，以及简单的修改

> by 2018-08-30
* 创作组建可用 ng generate component name
* 了解 app.model.ts内 [@NgModule](https://segmentfault.com/a/1190000007187393?utm_source=tuicool&utm_medium=referral) 各个部分的作用
interface NgModule {
     // providers: 这个选项是一个数组,需要我们列出我们这个模块的一些需要共用的服务
     //            然后我们就可以在这个模块的各个组件中通过依赖注入使用了.
    providers : Provider[]
     // declarations: 数组类型的选项, 用来声明属于这个模块的指令,管道等等.
     //               然后我们就可以在这个模块中使用它们了.
    declarations : Array<Type<any>|any[]>
     // imports: 数组类型的选项,我们的模块需要依赖的一些其他的模块,这样做的目的使我们这个模块
     //          可以直接使用别的模块提供的一些指令,组件等等.
    imports : Array<Type<any>|ModuleWithProviders|any[]>
     // exports: 数组类型的选项,我们这个模块需要导出的一些组件,指令,模块等;
     //          如果别的模块导入了我们这个模块,
     //          那么别的模块就可以直接使用我们在这里导出的组件,指令模块等.
    exports : Array<Type<any>|any[]>
    // entryComponents: 数组类型的选项,指定一系列的组件,这些组件将会在这个模块定义的时候进行编译
    //                  Angular会为每一个组件创建一个ComponentFactory然后把它存储在ComponentFactoryResolver
    entryComponents : Array<Type<any>|any[]>
    // bootstrap: 数组类型选项, 指定了这个模块启动的时候应该启动的组件.当然这些组件会被自动的加入到entryComponents中去
    bootstrap : Array<Type<any>|any[]>
    // schemas: 不属于Angular的组件或者指令的元素或者属性都需要在这里进行声明.
    schemas : Array<SchemaMetadata|any[]>
    // id: 字符串类型的选项,模块的隐藏ID,它可以是一个名字或者一个路径;用来在getModuleFactory区别模块,如果这个属性是undefined
    //     那么这个模块将不会被注册.
    id : string
 }
