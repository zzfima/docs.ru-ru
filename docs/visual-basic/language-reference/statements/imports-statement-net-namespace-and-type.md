---
title: Оператор Imports — пространство имен и тип .NET
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
ms.openlocfilehash: 39fa4e74f973bcb575b5751c387c0b879f4e398d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351072"
---
# <a name="imports-statement-net-namespace-and-type"></a>Оператор Imports (пространство имен .NET и тип)

Позволяет ссылаться на имена типов без уточнения пространства имен.

## <a name="syntax"></a>Синтаксис

```vb
Imports [ aliasname = ] namespace
' -or-
Imports [ aliasname = ] namespace.element
```

## <a name="parts"></a>Части

|Термин|Определение|
|---|---|
|`aliasname`|Необязательно. Псевдоним или имя *импорта* , по которому код может ссылаться на `namespace` вместо полной уточняющей строки. См. раздел [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).|
|`namespace`|Обязательно. Полное имя импортируемого пространства имен. Может быть строкой пространств имен, вложенных в любой уровень.|
|`element`|Необязательно. Имя программного элемента, объявленного в пространстве имен. Может быть любым элементом контейнера.|

## <a name="remarks"></a>Заметки

Оператор `Imports` позволяет напрямую ссылаться на типы, содержащиеся в данном пространстве имен.

Можно указать одно имя пространства имен или строку вложенных пространств имен. Каждое вложенное пространство имен отделяется от следующего пространства имен более высокого уровня на точку (`.`), как показано в следующем примере:

```vb
Imports System.Collections.Generic
```

Каждый исходный файл может содержать любое количество инструкций `Imports`. Они должны следовать любым объявлениям параметров, таким как оператор `Option Strict`, и должны предшествовать объявлениям элементов программирования, таким как `Module` или операторы `Class`.

`Imports` можно использовать только на уровне файлов. Это означает, что контекст объявления для импорта должен быть исходным файлом и не может быть пространством имен, классом, структурой, модулем, интерфейсом, процедурой или блоком.

Обратите внимание, что инструкция `Imports` не делает элементы из других проектов и сборок доступными для проекта. Импорт не является местом установки ссылки. Он только устраняет необходимость уточнять имена, которые уже доступны для проекта. Дополнительные сведения см. в разделе "Импорт содержащихся элементов" в [ссылках на объявленные элементы](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).

> [!NOTE]
> Можно определить неявные `Imports` инструкции с помощью [страницы ссылки, конструктора проектов (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic). Дополнительные сведения см. [в разделе инструкции. Добавление или удаление импортированных пространств имен (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic).

## <a name="import-aliases"></a>Импорт псевдонимов

*Псевдоним импорта* определяет псевдоним для пространства имен или типа. Псевдонимы импорта полезны, когда необходимо использовать элементы с одинаковыми именами, объявленными в одном или нескольких пространствах имен. Дополнительные сведения и пример см. в разделе "уточнение имени элемента в [ссылках на объявленные элементы](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)".

Не следует объявлять элемент на уровне модуля с тем же именем, что и `aliasname`. В этом случае компилятор Visual Basic использует `aliasname` только для объявленного элемента и больше не распознает его как псевдоним импорта.

Хотя синтаксис, используемый для объявления псевдонима импорта, похож на тот, который используется для импорта префикса пространства имен XML, результаты различаются. Псевдоним импорта можно использовать как выражение в коде, тогда как префикс пространства имен XML можно использовать только в литералах XML или свойствах оси XML в качестве префикса для полного имени элемента или атрибута.

### <a name="element-names"></a>Имена элементов

При указании `element`он должен представлять элемент- *контейнер*, то есть программный элемент, который может содержать другие элементы. Контейнерные элементы включают классы, структуры, модули, интерфейсы и перечисления.

Область действия элементов, доступных для оператора `Imports`, зависит от того, задается ли `element`. Если указать только `namespace`, все члены этого пространства имен с уникальными именами и элементы контейнеров внутри этого пространства имен будут доступны без квалификации. Если указать как `namespace`, так и `element`, только члены этого элемента будут доступны без квалификации.

## <a name="example"></a>Пример

В следующем примере возвращаются все папки в каталоге *C:\\* с помощью класса <xref:System.IO.DirectoryInfo>:

В коде нет инструкций `Imports` в верхней части файла. Таким образом, ссылки на <xref:System.IO.DirectoryInfo>, <xref:System.Text.StringBuilder>и <xref:Microsoft.VisualBasic.ControlChars.CrLf> полностью дополнены пространствами имен.

[!code-vb[VbVbalrStatements#152](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#152)]

## <a name="example"></a>Пример

В следующем примере содержатся `Imports` операторы для пространств имен, на которые имеются ссылки. Поэтому типы не обязательно должны быть полными с помощью пространств имен.

[!code-vb[VbVbalrStatements#153](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#153)]

[!code-vb[VbVbalrStatements#154](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#154)]
  
## <a name="example"></a>Пример

В следующем примере содержатся инструкции `Imports`, которые создают псевдонимы для упоминаемых пространств имен. Типы дополнены псевдонимами.

[!code-vb[VbVbalrStatements#155](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#155)]

[!code-vb[VbVbalrStatements#156](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#156)]

## <a name="example"></a>Пример

В следующем примере содержатся инструкции `Imports`, которые создают псевдонимы для ссылочных типов. Для указания типов используются псевдонимы.

[!code-vb[VbVbalrStatements#157](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#157)]

[!code-vb[VbVbalrStatements#158](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#158)]
  
## <a name="see-also"></a>См. также

- [Оператор Namespace](namespace-statement.md)
- [Пространства имен в Visual Basic](../../programming-guide/program-structure/namespaces.md)
- [Ссылки и оператор Imports](../../programming-guide/program-structure/references-and-the-imports-statement.md)
- [Оператор Imports (пространство имен XML)](imports-statement-xml-namespace.md)
- [Ссылки на объявленные элементы](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
