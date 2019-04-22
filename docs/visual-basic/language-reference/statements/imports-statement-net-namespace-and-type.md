---
title: Оператор Imports - пространство имен .NET и тип (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: 4574bab62ca6d095ab66c17bf186da5f3d79bfb7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58826526"
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
|`aliasname`|Необязательный параметр. *Псевдоним импорта* или имя, по которому код может обращаться к `namespace` вместо полной строки. См. раздел [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`namespace`|Обязательный. Полное имя импортируемого пространства имен. Могут быть строкой пространства имен, на которое имеется вложенными на любом уровне.|  
|`element`|Необязательный параметр. Имя элемента программирования, объявленные в пространстве имен. Может быть любой элемент-контейнер.|  
  
## <a name="remarks"></a>Примечания  
 `Imports` Инструкция включает типы, содержащиеся в заданном пространстве имен напрямую ссылаться на.  
  
 Можно указать имя одного пространства имен или строка вложенных пространств имен. Каждый вложенное пространство имен, отделенное точкой из следующего выше уровня пространства имен (`.`), как показано в следующем примере.  
  
 `Imports System.Collections.Generic`  
  
 Каждый исходный файл может содержать любое количество `Imports` инструкций. Они должны следовать за любым параметром объявления, такие как `Option Strict` инструкции и они должны предшествовать всем объявлениям программирования элемент, такой как `Module` или `Class` инструкций.  
  
 Можно использовать `Imports` только на уровне файлов. Это означает, что контекст объявления для импорта должен быть исходным файлом и не может быть пространство имен, класса, структуры, модуля, интерфейса, процедуры или блока.  
  
 Обратите внимание, что `Imports` инструкции не делает элементы из других проектов и сборок для проекта. Импорт не замещать ссылку. Он только избавляет от необходимости для уточнения имен, которые уже доступны в проекте. Дополнительные сведения см. в разделе «Импорт элементов с содержимым» в [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
> [!NOTE]
>  Вы можете определить неявные `Imports` , используя [страница "ссылки", конструктор проектов (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic). Дополнительные сведения см. в разделе [Как Добавление или удаление импортированных пространств имен (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic).  
  
## <a name="import-aliases"></a>Импорт псевдонимов  
 *Псевдоним импорта* определяет псевдоним для пространства имен или типа. Импорт псевдонимов полезны в тех случаях, когда необходимо использовать элементы с тем же именем, которые были определены в один или несколько пространств имен. Дополнительные сведения и пример см. в разделе «Уточнение имя элемента» в [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
 Участник на уровне модуля с тем же именем, что не следует объявлять `aliasname`. В противном случае компилятор Visual Basic использует `aliasname` только для объявленного элемента и больше не распознает его как псевдоним импорта.  
  
 Несмотря на то, что подобное синтаксис, используемый для объявления псевдонима импорта используется для импорта префикс пространства имен XML, результаты будут другими. Псевдоним импорта может использоваться как выражение в коде, тогда как префикс пространства имен XML можно использовать только в XML-литералов или свойств оси XML как префикс для элемента или имя атрибута.  
  
### <a name="element-names"></a>Имена элементов  
 Если вы указали `element`, он должен представлять *элемент-контейнер*, то есть программный элемент, который может содержать другие элементы. Элементы контейнера включают классы, структуры, модули, интерфейсы и перечисления.  
  
 Область элементов, предоставленных `Imports` инструкция зависит от того, указаны ли `element`. Если указать только `namespace`, все однозначно с именем из этого пространства имен и члены элементов-контейнеров в этом пространстве имен, доступны без уточнения. Если задан и `namespace` и `element`только члены этого элемента, доступны без уточнения.  
  
## <a name="example"></a>Пример  
 Следующий пример возвращает все папки в каталоге C:\, используя <xref:System.IO.DirectoryInfo> класса.  
  
 Код не имеет `Imports` инструкций в верхней части файла. Таким образом `DirectoryInfo`, <xref:System.Text.StringBuilder>, и <xref:Microsoft.VisualBasic.ControlChars.CrLf> ссылки являются все полное имя пространства имен.  
  
 [!code-vb[VbVbalrStatements#152](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#152)]  
  
## <a name="example"></a>Пример  
 В следующем примере `Imports` инструкций для пространств имен, на которую указывает ссылка. Таким образом типы не должны быть полным с пространствами имен.  
  
 [!code-vb[VbVbalrStatements#153](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#153)]  
  
 [!code-vb[VbVbalrStatements#154](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#154)]  
  
## <a name="example"></a>Пример  
 В следующем примере `Imports` инструкций, создающих псевдонимы для пространств имен, на которую указывает ссылка. Типы являются уточненными с псевдонимами.  
  
 [!code-vb[VbVbalrStatements#155](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#155)]  
  
 [!code-vb[VbVbalrStatements#156](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#156)]  
  
## <a name="example"></a>Пример  
 В следующем примере `Imports` инструкций, создающих псевдонимы для ссылочных типов. Псевдонимы используются для указания типов.  
  
 [!code-vb[VbVbalrStatements#157](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#157)]  
  
 [!code-vb[VbVbalrStatements#158](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#158)]  
  
## <a name="see-also"></a>См. также

- [Оператор Namespace](../../../visual-basic/language-reference/statements/namespace-statement.md)
- [Пространства имен в Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [Ссылки и оператор Imports](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)
- [Оператор Imports (пространство имен XML)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)
- [Ссылки на объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
