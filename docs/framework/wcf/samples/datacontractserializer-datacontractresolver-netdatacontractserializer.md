---
title: "Использование DataContractSerializer и Data Contract Resolver для обеспечения функциональности NetDataContractSerializer | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1376658f-f695-45f7-a7e0-94664e9619ff
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# Использование DataContractSerializer и Data Contract Resolver для обеспечения функциональности NetDataContractSerializer
В образце описывается, как использование <xref:System.Runtime.Serialization.DataContractSerializer> с соответствующим <xref:System.Runtime.Serialization.DataContractResolver> обеспечивает функциональность, идентичную <xref:System.Runtime.Serialization.NetDataContractSerializer>.В следующем образце показано, как создать соответствующий <xref:System.Runtime.Serialization.DataContractResolver> и как добавить его к <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
## Подробные сведения об образце  
 Существует одно важное отличие <xref:System.Runtime.Serialization.NetDataContractSerializer> от <xref:System.Runtime.Serialization.DataContractSerializer>: <xref:System.Runtime.Serialization.NetDataContractSerializer> включает информацию о типе CLR в сериализованный XML, а <xref:System.Runtime.Serialization.DataContractSerializer> этого не делает.Таким образом <xref:System.Runtime.Serialization.NetDataContractSerializer> может использоваться только при использовании одних и тех же типов CLR на концах сериализации и десериализации.Однако рекомендуется использовать <xref:System.Runtime.Serialization.DataContractSerializer>, поскольку он обладает более высоким уровнем производительности, чем <xref:System.Runtime.Serialization.NetDataContractSerializer>.Можно изменить данные, сериализуемые в <xref:System.Runtime.Serialization.DataContractSerializer> при добавлении к нему <xref:System.Runtime.Serialization.DataContractResolver>.  
  
 Этот образец состоит из двух проектов.В первом проекте используется <xref:System.Runtime.Serialization.NetDataContractSerializer> для сериализации этого объекта.Во втором проекте используется <xref:System.Runtime.Serialization.DataContractSerializer> с <xref:System.Runtime.Serialization.DataContractResolver> для обеспечения функциональности, идентичной первому проекту.  
  
 В следующем примере кода показана реализация пользовательского <xref:System.Runtime.Serialization.DataContractResolver> с именем `MyDataContractResolver`, добавленного к <xref:System.Runtime.Serialization.DataContractSerializer> в проекте DCSwithDCR.  
  
```  
class MyDataContractResolver : DataContractResolver  
{  
    private XmlDictionary dictionary = new XmlDictionary();  
  
    public MyDataContractResolver()  
    {  
    }  
  
    // Used at deserialization  
    // Allows users to map xsi:type name to any Type   
    public override Type ResolveName(string typeName, string typeNamespace, DataContractResolver knownTypeResolver)  
    {  
        Type type = knownTypeResolver.ResolveName(typeName, typeNamespace, null);  
        if (type == null)  
        {  
            type = Type.GetType(typeName + ", " + typeNamespace);  
        }  
        return type;  
    }  
  
    // Used at serialization  
    // Maps any Type to a new xsi:type representation  
    public override void ResolveType(Type dataContractType, DataContractResolver knownTypeResolver, out XmlDictionaryString typeName, out XmlDictionaryString typeNamespace)  
    {  
        knownTypeResolver.ResolveType(dataContractType, null, out typeName, out typeNamespace);  
        if (typeName == null || typeNamespace == null)  
        {  
            XmlDictionary dictionary = new XmlDictionary();  
            typeName = dictionary.Add(dataContractType.FullName);  
            typeNamespace = dictionary.Add(dataContractType.Assembly.FullName);  
        }  
    }  
}  
  
```  
  
#### Использование этого образца  
  
1.  Откройте файл решения DCRSample.sln в среде [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  Щелкните правой кнопкой мыши файл решения и выберите **Свойства**.  
  
3.  В диалоговом окне **Страницы свойств решений**, ниже разделов **Общие свойства** и **Запускаемый проект**, выберите **Несколько запускаемых проектов:**.  
  
4.  Рядом с проектом **DCSwithDCR** выберите **Пуск** в раскрывающемся меню **Действие**.  
  
5.  Рядом с проектом **NetDCS** выберите **Пуск** в раскрывающемся меню **Действие**.  
  
6.  Нажмите кнопку **ОК**, чтобы закрыть диалоговое окно.  
  
7.  Для построения решения нажмите CTRL\+SHIFT\+B.  
  
8.  Чтобы запустить решение, нажмите клавиши CTRL\+F5.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WCF\Basic\Contract\Data\NetDcSasDcSwithDCR`  
  
## См. также