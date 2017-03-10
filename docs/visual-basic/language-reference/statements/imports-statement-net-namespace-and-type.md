---
title: "Оператор Imports (пространство имен .NET и тип) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Imports"
  - "imports"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "псевдонимы [Visual Basic], импорт"
  - "псевдонимы [Visual Basic], оператор Imports"
  - "элементы контейнера [Visual Basic]"
  - "объявленные имена элементов [Visual Basic], квалификация"
  - "объявленные элементы [Visual Basic], элементы контейнера"
  - "импортирование псевдонимов [Visual Basic]"
  - "импорт [Visual Basic]"
  - "Imports - оператор [Visual Basic]"
  - "Imports - оператор [Visual Basic], синтаксис"
  - "пространства имен [Visual Basic], импорт"
ms.assetid: 7062f8aa-d890-4232-9eed-92836e13fb6e
caps.latest.revision: 40
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 40
---
# Оператор Imports (пространство имен .NET и тип)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Позволяет обращаться к именам типов без уточнения пространства имен.  
  
## Синтаксис  
  
```  
Imports [ aliasname = ] namespace  
-or-  
Imports [ aliasname = ] namespace.element  
```  
  
## Части  
  
|||  
|-|-|  
|Термин|Определение|  
|`aliasname`|Необязательный.  *import alias* или имя, по которому код может обращаться к `namespace` вместо использования полной строки.  См. раздел [Имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`namespace`|Обязательный.  Полное имя пространства имен импортируемого.  Может быть строкой пространства имен, вложенного на любом уровне.|  
|`element`|Необязательный.  Имя элемента программирования, объявленное в пространстве имен.  Может быть любым элементом контейнера.|  
  
## Заметки  
 Оператор `Imports`  разрешает непосредственно ссылаться на типы, содержащиеся в заданном пространстве имен.  
  
 Можно указать имя одного пространства имен или строку из вложенных пространств имен.  Каждое вложенное пространство имен отделяется от следующего пространства имен более высокого уровня точкой \(`.`\), как показано в следующем примере.  
  
 `Imports System.Collections.Generic`  
  
 Каждый исходный файл может содержать любое количество операторов `Imports`.  Они должны следовать за любым параметром объявления, таким как инструкция `Option Strict`, и они должны предшествовать любому объявлению элементов программированию, например инструкциям `Module` или `Class`.  
  
 Можно использовать `Imports` только на уровне файла.  Это означает, что контекст объявления для импорта должен быть исходным файлом и не может быть пространством имен, классом, структурой, модулем, интерфейсом, процедурой или блоком.  
  
 Обратите внимание, что оператор `Imports` не разрешает текущему проекту получать доступ к элементам других проектов и сборок.  Импорт не принимает в качестве параметра ссылку.  Он только избавляет от необходимости квалификации имен, которые уже доступны проекту.  Дополнительные сведения содержатся в разделе "Импорт содержащих элементов" в [Ссылки на объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
> [!NOTE]
>  Можно определить неявные операторы `Imports`, используя [Страница "Ссылки" в конструкторе проектов \(Visual Basic\)](/visual-studio/ide/reference/references-page-project-designer-visual-basic).  Дополнительные сведения см. в разделе [Практическое руководство. Добавление или удаление импортированных пространств имен \(Visual Basic\)](../Topic/How%20to:%20Add%20or%20Remove%20Imported%20Namespaces%20\(Visual%20Basic\).md).  
  
## Импорт псевдонимов  
 *Псевдоним импорта* определяет псевдоним для типа или пространства имен.  Псевдонимы применяются, когда необходимо использовать элементы с одинаковыми именами, объявленные в одном или нескольких пространствах имен.  Дополнительные сведения и примеры см. в подразделе "Уточнение имени элемента" раздела [Ссылки на объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
 Нельзя объявлять элемент на уровне модуля с именем, совпадающим с `aliasname`.  Если это сделать, то компилятор Visual Basic воспримет `aliasname` только для объявленного элемента и больше не распознает его как псевдоним импорта.  
  
 Хотя синтаксис, используемый для объявления псевдонима импорта, такой же как используемый для импорта префикса пространства имен XML, результаты отличаются.  Псевдоним импорта может использоваться как выражение в коде, тогда как префикс пространства имен XML можно использовать только в XML\-литералах или свойствах XML\-оси как префикс для элемента или имени атрибута.  
  
### Имена элементов  
 Если указать `element`, он должен представлять *container element*, который является элементом программирования, содержащим другие элементы.  К элементам контейнера относятся классы, структуры, модули, интерфейсы и перечисления.  
  
 Область элементов, доступных с помощью оператора `Imports`, зависит от того, определяется ли `element`.  Если задано только `namespace`, то все члены и члены элементов контейнера этого пространства имен с уникальными именами в пределах этого пространства имен доступны без уточнения.  Если указать вместе `namespace` и `element`, без уточнения доступны только члены этого элемента.  
  
## Пример  
 В следующем примере возвращаются все папки в папке C:\\ с помощью класса<xref:System.IO.DirectoryInfo>.  
  
 В коде нет операторов `Imports` в начале файла.  Таким образом ссылки `DirectoryInfo` <xref:System.Text.StringBuilder>и <xref:Microsoft.VisualBasic.ControlChars.CrLf> являются полными, с пространствами имен.  
  
 [!code-vb[VbVbalrStatements#152](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/imports-statement-net-na_1.vb)]  
  
## Пример  
 Следующий пример включает оператор `Imports` для пространств имен, на которые стоит ссылка.  Таким образом типы не обязательно должны быть полными, с пространствами имен.  
  
 [!code-vb[VbVbalrStatements#153](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/imports-statement-net-na_2.vb)]  
  
 [!code-vb[VbVbalrStatements#154](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/imports-statement-net-na_3.vb)]  
  
## Пример  
 Следующий пример включает операторы `Imports`, создающие псевдонимы для пространств имен, на которые стоит ссылка.  Типы дополняются псевдонимами.  
  
 [!code-vb[VbVbalrStatements#155](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/imports-statement-net-na_4.vb)]  
  
 [!code-vb[VbVbalrStatements#156](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/imports-statement-net-na_5.vb)]  
  
## Пример  
 Следующий пример включает операторы `Imports`, создающие псевдонимы для типов, на которые стоит ссылка.  Псевдонимы используются для указания типов.  
  
 [!code-vb[VbVbalrStatements#157](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/imports-statement-net-na_6.vb)]  
  
 [!code-vb[VbVbalrStatements#158](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/imports-statement-net-na_7.vb)]  
  
## См. также  
 [Оператор Namespace](../../../visual-basic/language-reference/statements/namespace-statement.md)   
 [Пространства имен в Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)   
 [Ссылки и оператор Imports](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)   
 [Оператор Imports \(пространство имен XML\)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)   
 [Ссылки на объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)