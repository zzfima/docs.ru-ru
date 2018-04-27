---
title: Обработка XML-файла (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- XML comments [Visual Basic], parsing [Visual Basic]
ms.assetid: 78a15cd0-7708-4e79-85d1-c154b7a14a8c
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 86dae99f2d17a506a27cf491a76083df618ba27b
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="processing-the-xml-file-visual-basic"></a>Обработка XML-файла (Visual Basic)
Компилятор создает строку идентификатора для каждой конструкции в коде, помеченной для создания документации. (Сведения о том, как для маркировки кода см. в разделе [теги XML-комментариев](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md).) Строка идентификатора однозначно определяет конструкцию. Программы обработки XML-файла можно использовать строку идентификатора для идентификации соответствующего [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] элемента метаданных или отражения.  
  
 XML-файл не представляет собой иерархическое представление кода; Это список с созданным Идентификатором для каждого элемента.  
  
 Компилятор соблюдает следующие правила при формировании строк идентификаторов.  
  
-   Без пробелов помещается в строку.  
  
-   Первая часть строки идентификатора определяет тип члена идентифицируется в виде одного символа, за которым следует двоеточие. Используются следующие типы членов.  
  
|Знак|Описание|  
|---|---|  
|в|namespace<br /><br /> Не удается добавить комментарии к документации к пространству имен, но можно сделать CREF ссылки на них, если она поддерживается.|  
|T|Тип: `Class`, `Module`, `Interface`, `Structure`, `Enum`, `Delegate`|  
|C|поле: `Dim`|  
|С|свойство: `Property` (включая свойства по умолчанию)|  
|M|метод: `Sub`, `Function`, `Declare`, `Operator`|  
|E|Событие: `Event`|  
|!|текст ошибки<br /><br /> Остальная часть строки предоставляет сведения об ошибке. Компилятор Visual Basic создает сведения об ошибках для ссылок, которые не удается разрешить.|  
  
-   Во второй части `String` — полное имя элемента, начиная с корневого пространства имен. Имя элемента, включающий его тип и пространство имен разделенных точками. Если имя элемента содержит точки, они заменяются знаком решетки (#). Предполагается, что элемент не имеет знака непосредственно в имени. Например, полное имя `String` бы конструктор `System.String.#ctor`.  
  
-   Для свойств и методов, имеющих аргументы, список этих аргументов заключается в круглые скобки и указывается в конце. Если аргументы не используются, скобки отсутствуют. Аргументы разделяются запятыми. Кодировка каждого аргумента следует непосредственно из того, как он кодируется в [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] подписи.  
  
## <a name="example"></a>Пример  
 В следующем коде показано, как идентификатор строки для класса и его членов, создаются.  
  
 [!code-vb[VbVbcnXmlDocComments#10](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/processing-the-xml-file_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)  
 [Практическое руководство. Создание XML-документации](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
