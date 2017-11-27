---
title: "Оператор Imports (пространство имен .NET и тип)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Imports
- imports
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
caps.latest.revision: "40"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 46cc78c2fd039fb56fd4d1b797f2d09cbe95d317
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imports-statement-net-namespace-and-type"></a>Оператор Imports (пространство имен .NET и тип)
Разрешает типа ссылаться на них без указания полного имени пространства имен.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Imports [ aliasname = ] namespace  
-or-  
Imports [ aliasname = ] namespace.element  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`aliasname`|Необязательно. *Псевдоним импорта* или имя, по которому код может обращаться к `namespace` вместо полной строки. В разделе [имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`namespace`|Обязательный. Полное имя импортируемого пространства имен. Строка пространств имен вкладываются на любом уровне.|  
|`element`|Необязательно. Имя элемента программирования, объявленные в пространстве имен. Может быть любым элементом контейнера.|  
  
## <a name="remarks"></a>Примечания  
 `Imports` Инструкция включает типы, которые содержатся в пространстве имен напрямую ссылаться на.  
  
 Можно указать имя одного пространства имен или строку из вложенных пространств имен. Каждое вложенное пространство имен, разделенный точкой из следующего выше уровня пространства имен (`.`), как показано в следующем примере.  
  
 `Imports System.Collections.Generic`  
  
 Каждый исходный файл может содержать любое количество `Imports` инструкции. Они должны следовать за любым параметром объявления, такие как `Option Strict` инструкции и они должны предшествовать всем объявлениям программный элемент, такой как `Module` или `Class` инструкции.  
  
 Можно использовать `Imports` только на уровне файла. Это означает, что контекст объявления для импорта должен быть исходным файлом и не может быть пространства имен, класса, структуры, модуля, интерфейса, процедуры или блока.  
  
 Обратите внимание, что `Imports` инструкция не делает элементы из других проектов и сборок, доступная для проекта. Импорт не принимает вместо настройки ссылки. Он только избавляет от необходимости уточнять имена, которые уже доступны в проект. Дополнительные сведения см. в разделе «Импорт элементов с содержимым» в [ссылки на объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
> [!NOTE]
>  Можно определить неявные `Imports` , используя [страница "ссылки" в конструкторе проектов (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic). Дополнительные сведения см. в разделе [как: Добавление или удаление Импортируемые пространства имен (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic).  
  
## <a name="import-aliases"></a>Импорт псевдонимов  
 *Псевдоним импорта* определяет псевдоним для пространства имен или типа. Импорт псевдонимов полезны в тех случаях, когда необходимо использовать элементы с одинаковыми именами, объявленные в одну или несколько пространств имен. Дополнительные сведения и пример см. в разделе «Уточнение элемент Name» в [ссылки на объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
 Не следует объявлять элемента на уровне модуля с тем же именем, как `aliasname`. В противном случае компилятор Visual Basic использует `aliasname` только для объявленного элемента и больше не распознает его как псевдоним импорта.  
  
 Несмотря на то, что такие же синтаксис, используемый для объявления псевдонима импорта используется для импорта префикса пространства имен XML, результаты будут другими. Псевдоним импорта может использоваться как выражение в коде, тогда как префикс пространства имен XML можно использовать только в XML-литералов или свойств оси XML как префикс для элемента или имя атрибута.  
  
### <a name="element-names"></a>Имена элементов  
 При указании `element`, он должен представлять *элемент-контейнер*, то есть программный элемент, который может содержать другие элементы. Элементы контейнера включают классы, структуры, модули, интерфейсы и перечисления.  
  
 Область элементов, доступных по `Imports` инструкция зависит от того, указаны ли `element`. Если указать только `namespace`, однозначно все именованные члены этого пространства имен и члены элементов контейнера в этом пространстве имен, доступны без уточнения. Если заданы оба `namespace` и `element`только члены этого элемента доступны без уточнения.  
  
## <a name="example"></a>Пример  
 Следующий пример возвращает все папки в каталоге C:\, используя <xref:System.IO.DirectoryInfo> класса.  
  
 Код не имеет `Imports` инструкции в верхней части файла. Таким образом `DirectoryInfo`, <xref:System.Text.StringBuilder>, и <xref:Microsoft.VisualBasic.ControlChars.CrLf> ссылки являются все полное с пространствами имен.  
  
 [!code-vb[VbVbalrStatements#152](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_1.vb)]  
  
## <a name="example"></a>Пример  
 Следующий пример содержит `Imports` инструкции для пространства имен, на которую указывает ссылка. Таким образом типы не должны полностью соответствовать пространства имен.  
  
 [!code-vb[VbVbalrStatements#153](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_2.vb)]  
  
 [!code-vb[VbVbalrStatements#154](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_3.vb)]  
  
## <a name="example"></a>Пример  
 Следующий пример включает `Imports` инструкций, создающих псевдонимы для пространств имен на которую указывает ссылка. Типы квалифицируются с псевдонимами.  
  
 [!code-vb[VbVbalrStatements#155](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_4.vb)]  
  
 [!code-vb[VbVbalrStatements#156](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_5.vb)]  
  
## <a name="example"></a>Пример  
 Следующий пример включает `Imports` инструкций, создающих псевдонимы для ссылочных типов. Псевдонимы используются для указания типов.  
  
 [!code-vb[VbVbalrStatements#157](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_6.vb)]  
  
 [!code-vb[VbVbalrStatements#158](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_7.vb)]  
  
## <a name="see-also"></a>См. также  
 [Оператор Namespace](../../../visual-basic/language-reference/statements/namespace-statement.md)  
 [Пространства имен в Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [Ссылки и оператор Imports](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)  
 [Оператор Imports (пространство имен XML)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)  
 [Ссылки на объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
