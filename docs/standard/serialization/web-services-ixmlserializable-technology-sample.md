---
title: "Образец технологии веб-служб IXmlSerializable"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0202d3f1-a50b-427d-a5bb-79208b8f1c22
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 72c7e9e1cbf47dd54726a16ddeb58a193d62dc31
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="web-services-ixmlserializable-technology-sample"></a>Образец технологии веб-служб IXmlSerializable
[Скачать образец](http://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Xml%20Serialization/IXmlSerializable.zip.exe)  
  
 В этом образце показано, как использовать объект <xref:System.Xml.Serialization.IXmlSerializable> для управления сериализацией пользовательских типов в веб-службах ASP.NET.  
  
### <a name="to-build-the-sample-using-visual-studio"></a>Сборка образца с использованием Visual Studio  
  
1.  Откройте [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] и выберите в меню **Файл** пункт **Новый веб-сайт**.  
  
2.  В левой области диалогового окна **Новый веб-сайт** выберите нужный язык программирования, а затем в правой области выберите **Веб-служба ASP.NET**.  
  
3.  Введите **IXmlSerializable** в качестве имени новой веб-службы.  
  
4.  В окне обозревателя решений щелкните правой кнопкой мыши значок файла Service.asmx и выберите команду **Удалить**. Повторите это действие для файла с кодом программной части Service.asmx.  
  
5.  Щелкните правой кнопкой мыши каталог проекта и выберите пункт **Добавить существующий элемент**. В диалоговом окне перейдите во вложенную папку "Служба" языкового каталога.  
  
6.  Выберите Service.asmx, затем повторите этот шаг для файла фонового кода Service.asmx.  
  
7.  Откройте [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)] и перейдите в каталог, который содержит каталог IXmlSerializable, созданный в шаге 3 выше.  
  
8.  Щелкните правой кнопкой мыши значок каталога IXmlSerializable и выберите пункт **Общий доступ и безопасность**.  
  
9. На вкладке "Общий доступ в Интернете" выберите **Открыть общий доступ к этой папке** и подтвердите параметры по умолчанию, включая имя IXmlSerializable.  
  
10. Нажмите кнопку **ОК**.  
  
### <a name="to-run-the-sample"></a>Выполнение образца  
  
1.  Откройте окно браузера и выделите адресную строку.  
  
2.  Введите адрес **http://localhost/IXmlSerializable/Service.asmx**.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Xml.Serialization.IXmlSerializable>  
 <xref:System.Xml.Serialization>  
 <xref:System.Xml.XmlConvert>  
 <xref:System.Xml.XmlQualifiedName>  
 <xref:System.Xml.XmlReader>  
 <xref:System.Xml.Schema.XmlSchema>  
 <xref:System.Xml.Schema.XmlSchemaSet>  
 <xref:System.Xml.XmlUrlResolver>  
 <xref:System.Xml.XmlWriter>
