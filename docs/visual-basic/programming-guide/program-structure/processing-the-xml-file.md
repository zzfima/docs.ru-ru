---
title: "Обработка XML-файла (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- XML comments, parsing [Visual Basic]
ms.assetid: 78a15cd0-7708-4e79-85d1-c154b7a14a8c
caps.latest.revision: 16
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: 72b2832d0131adf39a37ebd9297b43fb34ea49ba
ms.lasthandoff: 03/13/2017

---
# <a name="processing-the-xml-file-visual-basic"></a>Обработка XML-файла (Visual Basic)
Компилятор создает строку идентификатора для каждой конструкции в коде, отмеченной для создания документации. (Сведения о том, как для маркировки кода в разделе [теги XML-комментариев](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md).) Строка идентификатора однозначно определяет конструкцию. Программы обработки XML-файла можно использовать строку идентификатора для идентификации соответствующего [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] элемента метаданных или отражения.  
  
 XML-файл не является иерархическое представление кода; он содержит список с созданным Идентификатором для каждого элемента.  
  
 Компилятор должно соответствовать следующим правилам при формировании строк Идентификаторов:  
  
-   Отсутствует пробел не помещается в строку.  
  
-   Первая часть строки идентификатора определяет тип члена, идентифицированного в виде одного символа, за которым следует двоеточие. Используются следующие типы элементов.  
  
|Знак|Описание|  
|---|---|  
|в|namespace<br /><br /> Нельзя добавлять комментарии документации к пространству имен, но можно сделать CREF-ссылки на них, если они поддерживаются.|  
|T|type: `Class`, `Module`, `Interface`, `Structure`, `Enum`,`Delegate`|  
|C|поле:`Dim`|  
|С|свойство: `Property` (включая свойства по умолчанию)|  
|M|method: `Sub`, `Function`, `Declare`,`Operator`|  
|E|событие:`Event`|  
|!|Строка ошибки<br /><br /> Остальная часть строки предоставляет сведения об ошибке. [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Компилятор создает сведения об ошибках для ссылок, которые не удается разрешить.|  
  
-   Во второй части `String` полное имя элемента, начиная с корневого пространства имен. Имя элемента, включающий его тип и пространство имен разделяются точками. Если имя элемента содержит точки, они заменяются знаком решетки (#). Предполагается, что элемент не имеет знак решетки непосредственно в имени. Например, полное имя `String` бы конструктор `System.String.#ctor`.  
  
-   Для свойств и методов при наличии аргументов методу, следует список аргументов, заключенный в круглые скобки. Если не указано никаких аргументов, скобки отсутствуют. Аргументы разделяются запятыми. Кодировка каждого аргумента следует непосредственно из того, как он кодируется в [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] подписи.  
  
## <a name="example"></a>Пример  
 В следующем коде показано, как идентификатор строки для класса и его членов, создаются.  
  
 [!code-vb[VbVbcnXmlDocComments&#10;](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/processing-the-xml-file_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [/ doc](../../../visual-basic/reference/command-line-compiler/doc.md)   
 [Практическое руководство. Создание XML-документации](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
