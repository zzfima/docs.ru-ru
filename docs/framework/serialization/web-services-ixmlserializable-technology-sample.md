---
title: "Образец технологии веб-служб IXmlSerializable | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0202d3f1-a50b-427d-a5bb-79208b8f1c22
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Образец технологии веб-служб IXmlSerializable
[Загрузить образец](http://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Xml%20Serialization/IXmlSerializable.zip.exe)  
  
 В этом образце показано, как использовать объект <xref:System.Xml.Serialization.IXmlSerializable> для управления сериализацией пользовательских типов в веб\-службах ASP.NET.  
  
### Построение образца с использованием Visual Studio  
  
1.  Откройте [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] и выберите **Создать веб\-узел** из меню **Файл**.  
  
2.  В левой панели диалогового окна **Создать веб\-узел** выберите нужный язык программирования, затем на правой панели выберите **Веб\-служба ASP.NET**.  
  
3.  Введите **IXmlSerializable** в качестве имени новой веб\-службы.  
  
4.  В окне обозревателя решений щелкните правой кнопкой значок Service.asmx и выберите **Удалить**. Повторите этот шаг для файла фонового кода Service.asmx.  
  
5.  Щелкните правой кнопкой мыши каталог проекта и выберите пункт **Добавить существующий элемент**.В диалоговом окне перейдите во вложенную папку "Служба" языкового каталога.  
  
6.  Выберите Service.asmx, затем повторите этот шаг для файла фонового кода Service.asmx.  
  
7.  Откройте [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)] и перейдите в каталог, который содержит каталог IXmlSerializable, созданный в шаге 3 выше.  
  
8.  Щелкните правой кнопкой значок каталога IXmlSerializable и выберите команду **Общий доступ и безопасность**.  
  
9. Во вкладке "Доступ через веб" выберите **Открыть общий доступ к этой папке** и подтвердите параметры по умолчанию, включая имя IXmlSerializable.  
  
10. Нажмите кнопку **ОК**.  
  
### Выполнение примера  
  
1.  Откройте окно браузера и выделите адресную строку.  
  
2.  Введите адрес **http:\/\/localhost\/IXmlSerializable\/Service.asmx**.  
  
## См. также  
 <xref:System.Xml.Serialization.IXmlSerializable>   
 <xref:System.Xml.Serialization>   
 <xref:System.Xml.XmlConvert>   
 <xref:System.Xml.XmlQualifiedName>   
 <xref:System.Xml.XmlReader>   
 <xref:System.Xml.Schema.XmlSchema>   
 <xref:System.Xml.Schema.XmlSchemaSet>   
 <xref:System.Xml.XmlUrlResolver>   
 <xref:System.Xml.XmlWriter>