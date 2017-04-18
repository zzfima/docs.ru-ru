---
title: "Оператор Imports (пространство имен .NET и тип) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Imports
- imports
dev_langs:
- VB
helpviewer_keywords:
- declared element names [Visual Basic], qualification
- imports [Visual Basic]
- Imports statement [Visual Basic]
- aliases [Visual Basic], Imports statement
- container elements [Visual Basic]
- namespaces [Visual Basic], importing
- Imports statement [Visual Basic], syntax
- import aliases [Visual Basic]
- aliases [Visual Basic], import
- declared elements [Visual Basic], container elements
ms.assetid: 7062f8aa-d890-4232-9eed-92836e13fb6e
caps.latest.revision: 40
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
ms.openlocfilehash: 393f3e9a264817d8658585267c954d973290530a
ms.lasthandoff: 03/13/2017

---
# <a name="imports-statement-net-namespace-and-type"></a>Оператор Imports (пространство имен .NET и тип)
Разрешает типа ссылаться на них без квалификации пространства имен.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Imports [ aliasname = ] namespace  
-or-  
Imports [ aliasname = ] namespace.element  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`aliasname`|Необязательный. *Псевдоним импорта* или имя, по которому код может обращаться к `namespace` вместо полной строки. В разделе [имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`namespace`|Обязательный. Полное имя импортируемого пространства имен. Можно строкой пространства имен располагаться на любом уровне.|  
|`element`|Необязательный. Имя элемента программирования, объявленного в пространстве имен. Может быть любым элементом контейнера.|  
  
## <a name="remarks"></a>Примечания  
 `Imports` Инструкция включает содержащиеся в заданном пространстве имен непосредственно ссылаться на типы.  
  
 Можно указать имя одного пространства имен или строку из вложенных пространств имен. Каждое вложенное пространство имен отделяется от следующего уровня выше пространство имен точкой (`.`), как показано в следующем примере.  
  
 `Imports System.Collections.Generic`  
  
 Каждый исходный файл может содержать любое количество `Imports` инструкции. Они должны следовать за любым параметром объявления, такие как `Option Strict` инструкции и они должны предшествовать любому объявлению элементов программированию, такие как `Module` или `Class` инструкции.  
  
 Можно использовать `Imports` только на уровне файла. Это означает, что контекст объявления для импорта должен быть исходным файлом и не может быть пространство имен, класс, структура, модуль, интерфейса, процедуры или блока.  
  
 Обратите внимание, что `Imports` инструкция не делает элементы из других проектов и сборок, доступны в проекте. Импорт не выполняться ссылку. Он только избавляет от необходимости уточнять имена, которые уже доступны в проект. Дополнительные сведения см. в разделе «Импорт содержащих элементов» в [ссылки на объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
> [!NOTE]
>  Можно определить неявные `Imports` инструкций с помощью [страница "ссылки" в конструкторе проектов (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic). Дополнительные сведения см. в разделе [Практическое руководство: Добавление или удаление Импортируемые пространства имен (Visual Basic)](http://msdn.microsoft.com/library/44cebec3-0ea0-47c2-8406-4edeab6a997e).  
  
## <a name="import-aliases"></a>Импорт псевдонимов  
 *Псевдоним импорта* определяет псевдоним для пространства имен или типа. Псевдонимы применяются, когда необходимо использовать элементы с одинаковыми именами, объявленные в одну или несколько пространств имен. Дополнительные сведения и пример см. в разделе «Определение элемента Name» в [ссылки на объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
 Не следует объявлять элемент на уровне модуля с тем же именем, как `aliasname`. В противном случае компилятор Visual Basic использует `aliasname` только для объявленного элемента и больше не распознает его как псевдоним импорта.  
  
 Хотя синтаксис, используемый для объявления псевдонима импорта подобного используется для импорта префикса пространства имен XML, результаты будут другими. Псевдоним импорта может использоваться как выражение в коде, тогда как префикс пространства имен XML можно использовать только в XML-литералов или свойств оси XML как префикс для элемента или имени атрибута.  
  
### <a name="element-names"></a>Имена элементов  
 При указании `element`, он должен представлять *элемент-контейнер*, то есть элемент программирования, может содержать другие элементы. Элементы контейнера включают классы, структуры, модули, интерфейсы и перечисления.  
  
 Область элементов, доступных по `Imports` инструкция зависит от того, указаны ли `element`. Если указать только `namespace`, однозначно все члены этого пространства имен и члены элементов контейнера в этом пространстве имен, доступны без уточнения. Если указываются оба `namespace` и `element`только члены этого элемента будут доступны без уточнения.  
  
## <a name="example"></a>Пример  
 Следующий пример возвращает все папки в каталоге C:\ с помощью <xref:System.IO.DirectoryInfo>класса.</xref:System.IO.DirectoryInfo>  
  
 Код не имеет `Imports` в начало файла. Таким образом `DirectoryInfo`, <xref:System.Text.StringBuilder>, и <xref:Microsoft.VisualBasic.ControlChars.CrLf>ссылки являются полностью полного пространства имен.</xref:Microsoft.VisualBasic.ControlChars.CrLf> </xref:System.Text.StringBuilder>  
  
 [!code-vb[VbVbalrStatements&#152;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_1.vb)]  
  
## <a name="example"></a>Пример  
 Следующий пример включает `Imports` инструкции для пространств имен, на которые имеются ссылки. Таким образом типы не должны полностью соответствовать пространства имен.  
  
 [!code-vb[VbVbalrStatements&#153;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_2.vb)]  
  
 [!code-vb[VbVbalrStatements&#154;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_3.vb)]  
  
## <a name="example"></a>Пример  
 Следующий пример включает `Imports` инструкции, создающие псевдонимы для пространств имен, на которые имеются ссылки. Типы будут дополнены псевдонимы.  
  
 [!code-vb[VbVbalrStatements&#155;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_4.vb)]  
  
 [!code-vb[VbVbalrStatements&#156;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_5.vb)]  
  
## <a name="example"></a>Пример  
 Следующий пример включает `Imports` инструкции, создающие псевдонимы для ссылочных типов. Псевдонимы используются для указания типов.  
  
 [!code-vb[VbVbalrStatements&#157;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_6.vb)]  
  
 [!code-vb[VbVbalrStatements&#158;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_7.vb)]  
  
## <a name="see-also"></a>См. также  
 [Оператор Namespace](../../../visual-basic/language-reference/statements/namespace-statement.md)   
 [Пространства имен в Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)   
 [Ссылки и оператор Imports](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)   
 [Оператор Imports (пространство имен XML)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)   
 [Ссылки на объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
