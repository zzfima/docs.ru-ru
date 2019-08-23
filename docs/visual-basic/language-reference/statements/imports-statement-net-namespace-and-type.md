---
title: Оператор Imports — пространство имен и тип .NET (Visual Basic)
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
ms.openlocfilehash: a0b7a6a5fd16dc0daa620e6b490ddfdeb0e7c80e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912391"
---
# <a name="imports-statement-net-namespace-and-type"></a>Оператор Imports (пространство имен .NET и тип)
Позволяет ссылаться на имена типов без уточнения пространства имен.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Imports [ aliasname = ] namespace  
-or-  
Imports [ aliasname = ] namespace.element  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`aliasname`|Необязательный параметр. Псевдоним или имя *импорта* , по которому может ссылаться `namespace` код вместо полной уточняющей строки. См. раздел [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`namespace`|Обязательный. Полное имя импортируемого пространства имен. Может быть строкой пространств имен, вложенных в любой уровень.|  
|`element`|Необязательный параметр. Имя программного элемента, объявленного в пространстве имен. Может быть любым элементом контейнера.|  
  
## <a name="remarks"></a>Примечания  
 `Imports` Оператор позволяет напрямую ссылаться на типы, содержащиеся в данном пространстве имен.  
  
 Можно указать одно имя пространства имен или строку вложенных пространств имен. Каждое вложенное пространство имен отделяется от следующего пространства имен более высокого уровня точкой`.`(), как показано в следующем примере.  
  
 `Imports System.Collections.Generic`  
  
 Каждый исходный файл может содержать любое количество `Imports` инструкций. Они должны следовать любым объявлениям параметров, таким как `Option Strict` оператор, и должны предшествовать любым объявлениям элементов программирования, таким как `Module` операторы или `Class` .  
  
 Можно использовать `Imports` только на уровне файлов. Это означает, что контекст объявления для импорта должен быть исходным файлом и не может быть пространством имен, классом, структурой, модулем, интерфейсом, процедурой или блоком.  
  
 Обратите внимание `Imports` , что инструкция не делает элементы из других проектов и сборок доступными для проекта. Импорт не является местом установки ссылки. Он только устраняет необходимость уточнять имена, которые уже доступны для проекта. Дополнительные сведения см. в разделе "Импорт содержащихся элементов" в [ссылках на объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
> [!NOTE]
> Неявные `Imports` инструкции можно определить с помощью [страницы ссылки в конструкторе проектов (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic). Дополнительные сведения см. в разделе [Практическое руководство. Добавление или удаление импортированных пространств имен (Visual Basic](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic)).  
  
## <a name="import-aliases"></a>Импорт псевдонимов  
 *Псевдоним импорта* определяет псевдоним для пространства имен или типа. Псевдонимы импорта полезны, когда необходимо использовать элементы с одинаковыми именами, объявленными в одном или нескольких пространствах имен. Дополнительные сведения и пример см. в разделе "уточнение имени элемента в ссылках [на объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)".  
  
 Не следует объявлять элемент на уровне модуля с тем же именем, что `aliasname`и. В этом случае компилятор Visual Basic использует `aliasname` только для объявленного элемента и больше не распознает его как псевдоним импорта.  
  
 Хотя синтаксис, используемый для объявления псевдонима импорта, похож на тот, который используется для импорта префикса пространства имен XML, результаты различаются. Псевдоним импорта можно использовать как выражение в коде, тогда как префикс пространства имен XML можно использовать только в литералах XML или свойствах оси XML в качестве префикса для полного имени элемента или атрибута.  
  
### <a name="element-names"></a>Имена элементов  
 При указании `element`он должен представлять элемент- *контейнер*, то есть программный элемент, который может содержать другие элементы. Контейнерные элементы включают классы, структуры, модули, интерфейсы и перечисления.  
  
 Область действия элементов, доступных для `Imports` инструкции, зависит от того, указан `element`ли параметр. Если указать только `namespace`, то все члены этого пространства имен с уникальными именами и элементы контейнеров внутри этого пространства имен будут доступны без квалификации. Если указать `namespace` и, и `element`, то только элементы этого элемента будут доступны без квалификации.  
  
## <a name="example"></a>Пример  
 В следующем примере возвращаются все папки в папке C:\. каталог с помощью <xref:System.IO.DirectoryInfo> класса.  
  
 Код не содержит `Imports` операторов в верхней части файла. Таким образом, `DirectoryInfo`ссылки <xref:System.Text.StringBuilder>, и <xref:Microsoft.VisualBasic.ControlChars.CrLf> полностью определены с помощью пространств имен.  
  
 [!code-vb[VbVbalrStatements#152](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#152)]  
  
## <a name="example"></a>Пример  
 В следующем примере содержатся `Imports` инструкции для пространств имен, на которые имеются ссылки. Поэтому типы не обязательно должны быть полными с помощью пространств имен.  
  
 [!code-vb[VbVbalrStatements#153](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#153)]  
  
 [!code-vb[VbVbalrStatements#154](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#154)]  
  
## <a name="example"></a>Пример  
 В следующем примере содержатся `Imports` инструкции, создающие псевдонимы для упоминаемых пространств имен. Типы дополнены псевдонимами.  
  
 [!code-vb[VbVbalrStatements#155](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#155)]  
  
 [!code-vb[VbVbalrStatements#156](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#156)]  
  
## <a name="example"></a>Пример  
 В следующем примере содержатся `Imports` инструкции, создающие псевдонимы для ссылочных типов. Для указания типов используются псевдонимы.  
  
 [!code-vb[VbVbalrStatements#157](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#157)]  
  
 [!code-vb[VbVbalrStatements#158](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#158)]  
  
## <a name="see-also"></a>См. также

- [Оператор Namespace](../../../visual-basic/language-reference/statements/namespace-statement.md)
- [Пространства имен в Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [Ссылки и оператор Imports](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)
- [Оператор Imports (пространство имен XML)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)
- [Ссылки на объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
