---
title: "Мастер построения схемы на основе кода XML (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.XmlToSchemaWizard"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "IntelliSense [Visual Basic], XML"
  - "XML [Visual Basic], IntelliSense"
  - "XML IntelliSense [Visual Basic]"
  - "схемы XML, создание"
ms.assetid: 98c495ba-8f37-4517-a0db-aa738611ab76
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Мастер построения схемы на основе кода XML (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Используйте XML для мастера схем для создания XML\-схемы, которая является производной от одного или более XML\-документов и включает их в проект.  Можно использовать любые комбинации XML\-документов в форме текстовых файлов, XML из HTTP\-адресов или XML, который объявляется и передается в XML для мастера схем.  
  
 XML\-схемы используются для предоставления IntelliSense для свойств XML в Visual Basic.  Дополнительные сведения см. в разделах [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md) и [XML IntelliSense в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md).  
  
> [!NOTE]
>  Перед запуском XML для мастера схем рекомендуется удалить все существующие XSD\-файлы из проекта, ранее созданного мастером.  При получении XML\-схемы, которая совпадает с существующей схемой, может возникнуть конфликт и [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] не сможет предоставить IntelliSense для свойств XML.  
  
 XML для мастера схем использует класс <xref:System.Xml.Schema.XmlSchemaInference> для создания схем для заданного XML.  В результате для набора схем может быть создано несколько файлов\-схем.  Для каждого пространства имен XML в заданном XML создается XSD\-файл.  Дополнительные сведения см. в описании метода <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A>.  
  
 Чтобы обратиться к XML для мастера схем, нажмите **Добавить новый элемент** в меню **Проект** и добавьте шаблон **XML для схем** либо из группы шаблонов **Данные**, либо из группы шаблонов **Общие элементы**.  После включения всех источников XML\-документов для определения набора XML\-схем, нажмите **OK** для создания производного набора схем.  
  
 **Исходный тип**  
 Этот столбец отображает типы источников XML\-документов: **Файл**, **URL\-адрес** или **XML**.  
  
 **Расположение документа XML**  
 Этот столбец отображает путь к XML\-документу.  Для ввода или вставки XML\-документов, отобразите содержимое XML\-документа.  
  
 **Добавить из файла**  
 Нажмите эту кнопку, чтобы добавить файлы XML\-документов с помощью обозревателя файла.  
  
 **Добавить из интернета**  
 Нажмите эту кнопку, чтобы использовать HTTP\-адрес XML\-документа.  
  
 **Ввод или вставка XML**  
 Нажмите эту кнопку, чтобы ввести или вставить XML\-документ в диалоговое окно.  
  
## См. также  
 <xref:System.Xml.Schema.XmlSchemaInference>   
 [XML IntelliSense в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md)