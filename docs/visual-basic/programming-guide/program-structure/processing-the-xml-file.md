---
title: "Обработка XML-файла (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "XML-комментарии, синтаксический анализ [Visual Basic]"
ms.assetid: 78a15cd0-7708-4e79-85d1-c154b7a14a8c
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Обработка XML-файла (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Компилятор создает строку идентификатора для каждой конструкции в коде, отмеченной для создания документации  \(сведения о том, как использовать теги в коде, cм. в разделе [XML\-теги для комментариев](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)\). Строка идентификатора однозначно определяет конструкцию.  Программы обработки XML\-файлов могут использовать строку идентификатор для идентификации соответствующего элемента метаданных или отражений [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)].  
  
 XML\-файл не является иерархическим представлением кода; он содержит список с созданным идентификатором для каждого элемента.  
  
 Компилятор следует приведенным ниже правилам при формировании строк идентификаторов:  
  
-   Пробел не помещается в строку.  
  
-   Первая часть строки идентификатора определяет тип идентифицированного члена в виде одного символа с последующим двоеточием.  Используются следующие типы элементов.  
  
|||  
|-|-|  
|Знак|Описание|  
|N|namespace<br /><br /> Нельзя добавлять документированные комментарии к пространству имен, но можно сделать CREF\-ссылки на них, если они поддерживаются.|  
|T|Тип: `Class`, `Module`, `Interface`, `Structure`, `Enum`, `Delegate`|  
|F|Поле `Dim`|  
|P|Свойство `Property` \(включая свойства по умолчанию\)|  
|M|Метод `Sub`, `Function`, `Declare`, `Operator`|  
|E|Событие `Event`|  
|\!|Строка ошибки<br /><br /> Остальная часть строки содержит сведения об ошибке.  Компилятор [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] создает сведения об ошибках для ссылок, которые не могут быть разрешены.|  
  
-   Вторая часть `String` — это полное имя элемента, начиная с корневого пространства имен.  Имя элемента, включающий его тип и пространство имен разделяются точками.  Если имя элемента содержит точки, они заменяются решетками \(\#\).  Предполагается, что элемент не имеет символов решетки непосредственно в имени.  Например полное имя конструктора `String` будет `System.String.#ctor`.  
  
-   Для свойств и методов при наличии аргументов метода, список аргументов следует заключить в скобки.  Если аргументов нет, скобки отсутствуют.  Несколько аргументов разделяются запятыми.  Кодировка каждого аргумента следует непосредственно из того, как он кодируется в сигнатуре [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)].  
  
## Пример  
 В следующем коде показано как создаются строки идентификаторы для класса и его членов.  
  
 [!code-vb[VbVbcnXmlDocComments#10](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/processing-the-xml-file_1.vb)]  
  
## См. также  
 [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md)   
 [Практическое руководство. Создание XML\-документации](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)