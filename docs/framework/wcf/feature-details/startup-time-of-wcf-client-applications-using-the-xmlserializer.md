---
title: "Как сократить время запуска клиентских приложений WCF с использованием XmlSerializer | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 21093451-0bc3-4b1a-9a9d-05f7f71fa7d0
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Как сократить время запуска клиентских приложений WCF с использованием XmlSerializer
Службы и клиентские приложения, использующие типы данных, сериализуемые с помощью сериализатора <xref:System.Xml.Serialization.XmlSerializer>, создают и компилируют код сериализации для этих типов данных во время выполнения, что может привести к снижению производительности при запуске.  
  
> [!NOTE]
>  Предварительно созданный код сериализации может использоваться только в клиентских приложениях, но не в службах.  
  
 [Служебное средство ServiceModel Metadata Utility Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) может улучшить производительность при запуске этих приложений путем создания необходимого кода сериализации из скомпилированных сборок для приложения.Svcutil.exe создает код сериализации для всех типов данных, используемых в контрактах служб в скомпилированной сборке приложения, которые могут быть сериализованы с помощью <xref:System.Xml.Serialization.XmlSerializer>.Контракты служб и операций, предусматривающие использование <xref:System.Xml.Serialization.XmlSerializer>, отмечены атрибутом <xref:System.ServiceModel.XmlSerializerFormatAttribute>.  
  
### Создание кода сериализации XmlSerializer  
  
1.  Скомпилируйте код службы или клиента в одну или несколько сборок.  
  
2.  Откройте окно командной строки SDK.  
  
3.  Из командной строки запустите средство Svcutil.exe, используя следующий формат.  
  
    ```  
    svcutil.exe /t:xmlSerializer  <assemblyPath>*  
    ```  
  
     Аргумент `assemblyPath` задает путь к сборке, содержащей типы из контракта службы.Svcutil.exe создает код сериализации для всех типов данных, используемых в контрактах служб в скомпилированной сборке приложения, которые могут быть сериализованы с помощью <xref:System.Xml.Serialization.XmlSerializer>.  
  
     Svcutil.exe может формировать только код сериализации на C\#.Для каждой входной сборки создается один файл исходного кода.Изменить язык создаваемого кода с помощью переключателя **\/language** нельзя.  
  
     Чтобы задать путь к зависимым сборкам, используйте параметр **\/reference**.  
  
4.  Предоставьте приложению доступ к созданному коду сериализации одним из следующих способов.  
  
    1.  Скомпилируйте созданный код сериализации в отдельную сборку с именем \[*original assembly*\].XmlSerializers.dll \(например, MyApp.XmlSerializers.dll\).Приложение должно иметь возможность загрузить эту сборку, которая должна быть подписана с помощью того же ключа, что и исходная сборка.В случае повторной компиляции исходной сборки необходимо заново создать сборку сериализации.  
  
    2.  Скомпилируйте созданный код сериализации в отдельную сборку и используйте атрибут <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute> в контракте службы, в котором используется атрибут <xref:System.ServiceModel.XmlSerializerFormatAttribute>.Задайте свойство <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A> или <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A> так, чтобы оно указывало на скомпилированную сборку сериализации.  
  
    3.  Скомпилируйте созданный код сериализации в сборку приложения и добавьте атрибут <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute> в контракт службы, в котором используется атрибут <xref:System.ServiceModel.XmlSerializerFormatAttribute>.Не задавайте свойства <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A> или <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A>.По умолчанию предполагается, что сборка сериализации по умолчанию является текущей сборкой.  
  
## Пример  
 Следующая команда создает типы сериализации для типов `XmlSerializer`, используемых любыми контрактами служб в сборке.  
  
```  
svcutil /t:xmlserializer myContractLibrary.exe  
```  
  
## См. также  
 [Служебное средство ServiceModel Metadata Utility Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)