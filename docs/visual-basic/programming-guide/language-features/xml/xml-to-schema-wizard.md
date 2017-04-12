---
title: "XML для мастера схем (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vb.XmlToSchemaWizard
dev_langs:
- VB
helpviewer_keywords:
- XML IntelliSense [Visual Basic]
- XML [Visual Basic], IntelliSense
- IntelliSense [Visual Basic], XML
- XML schemas, creating
ms.assetid: 98c495ba-8f37-4517-a0db-aa738611ab76
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: d0c9c0247f3d9934ef973c7322cb098f9b445a5a
ms.lasthandoff: 03/13/2017

---
# <a name="xml-to-schema-wizard-visual-basic"></a>Мастер построения схемы на основе кода XML (Visual Basic)
Используйте XML для мастера схем для создания набор схем XML, который выводится из одного или нескольких XML-документов и включает их в проект. Можно использовать любую комбинацию XML-документов в виде текстовых файлов, XML из HTTP-адресов или XML, который объявляется и передается в XML для мастера схем.  
  
 XML-схемы используются для обеспечения поддержки технологии IntelliSense для свойств XML в Visual Basic. Дополнительные сведения см. в разделе [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md) и [XML IntelliSense в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md).  
  
> [!NOTE]
>  Перед запуском XML для мастера схем рекомендуется удалить все существующие файлы XSD из проекта, ранее созданного с помощью мастера. Если определить набор XML-схем, соответствующий существующий набор схем, может возникнуть конфликт и [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] не смогут предоставить IntelliSense для свойств XML.  
  
 XML для мастера схем использует <xref:System.Xml.Schema.XmlSchemaInference>класса для создания схемы XML, предоставленных.</xref:System.Xml.Schema.XmlSchemaInference> В результате для набора схем может создаваться несколько файлов схемы. Для каждого пространства имен XML в заданном XML создается файл расширяемый определения схемы (XSD). Дополнительные сведения см. в разделе <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A>метод.</xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A>  
  
 Для доступа к XML для мастера схем, нажмите кнопку **Добавление нового элемента** на **проекта** меню и добавьте **XML to Schema** шаблон либо из **данные** или **Общие элементы** группа шаблонов. После включения всех источников XML-документов, чтобы получить набор схем XML из щелкните **ОК** Создание схему набора.  
  
 **Тип источника**  
 В этом столбце отображается тип исходного документа XML: **файл**, **URL-адрес**, или **XML**.  
  
 **Расположение документа XML**  
 Этот столбец отображает путь к XML-документа. Для ввода или вставки XML-документов отображает содержимое XML-документа.  
  
 **Добавить из файла**  
 Нажмите эту кнопку, чтобы добавить файлы XML-документов с помощью проводника.  
  
 **Добавить из Интернета**  
 Нажмите эту кнопку, чтобы указать HTTP-адрес XML-документа.  
  
 **Введите или вставьте XML**  
 Нажмите эту кнопку, чтобы ввести или вставить XML-документа в диалоговом окне.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Xml.Schema.XmlSchemaInference></xref:System.Xml.Schema.XmlSchemaInference>   
 [XML IntelliSense в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md)
