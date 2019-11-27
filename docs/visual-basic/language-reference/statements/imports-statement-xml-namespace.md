---
title: Оператор Imports — пространство имен XML
ms.date: 07/20/2015
f1_keywords:
- vb.ImportsXmlns
helpviewer_keywords:
- XML namespace [Visual Basic], importing
- imports [Visual Basic]
- Imports statement [Visual Basic]
- namespaces [Visual Basic], importing
ms.assetid: 1f4d50a6-08c7-4c2e-8206-ccae35fcd1b4
ms.openlocfilehash: 52864e4d1c8183b6243025e72368d23627049c84
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351053"
---
# <a name="imports-statement-xml-namespace"></a>Оператор Imports (пространство имен XML)

Импортирует префиксы пространства имен XML для использования в XML-литералах и свойствах осей XML.

## <a name="syntax"></a>Синтаксис

```vb
Imports <xmlns:xmlNamespacePrefix = "xmlNamespaceName">
```

## <a name="parts"></a>Части

`xmlNamespacePrefix`  
Необязательный элемент. Строка, с помощью которой XML-элементы и атрибуты могут ссылаться на `xmlNamespaceName`. Если `xmlNamespacePrefix` не указан, импортированное пространство имен XML является пространством имен XML по умолчанию. Должен быть допустимым идентификатором XML. Дополнительные сведения см. в разделе [Имена объявленных XML-элементов и атрибутов](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).

`xmlNamespaceName`  
Обязательно. Строка, идентифицирующая импортируемое пространство имен XML.

## <a name="remarks"></a>Примечания

Можно использовать инструкцию `Imports` для определения глобальных пространств имен XML, которые можно использовать с XML-литералами и свойствами осей XML, или как параметры, передаваемые оператору `GetXmlNamespace`. (Сведения об использовании оператора `Imports` для импорта псевдонима, который можно использовать при использовании имен типов в коде, см. в разделе [оператор Imports (пространство имен .NET и тип)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).) Синтаксис объявления пространства имен XML с помощью оператора `Imports` идентичен синтаксису, используемому в XML. Таким образом, можно скопировать объявление пространства имен из XML-файла и использовать его в инструкции `Imports`.

Префиксы пространства имен XML полезны, если требуется многократно создавать XML-элементы из одного и того же пространства имен. Префикс пространства имен XML, объявленный с помощью оператора `Imports`, является глобальным в том смысле, что он доступен для всего кода в файле. Его можно использовать при создании литералов XML-элементов и при доступе к свойствам осей XML. Дополнительные сведения см. в разделе [литерал XML-элемента](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) и [Свойства оси XML](../../../visual-basic/language-reference/xml-axis/index.md).

Если определено глобальное пространство имен XML без префикса пространства имен (например, `Imports <xmlns="http://SomeNameSpace>"`), это пространство имен считается пространством имен XML по умолчанию. Пространство имен XML по умолчанию используется для любых литералов XML-элементов или свойств оси атрибутов XML, которые явно не задают пространство имен. Пространство имен по умолчанию также используется, если указанное пространство имен представляет собой пустое пространство имен (то есть `xmlns=""`). Пространство имен XML по умолчанию не применяется к атрибутам XML в XML-литералах или к свойствам оси атрибутов XML, не имеющим пространства имен.

Пространства имен XML, определенные в XML-литерале, которые называются *локальными пространствами имен XML*, имеют приоритет над пространствами имен XML, которые определены инструкцией `Imports` как глобальные. Пространства имен XML, определенные оператором `Imports`, имеют приоритет над пространствами имен XML, импортированными для проекта Visual Basic. Если XML-литерал определяет пространство имен XML, это локальное пространство имен не применяется к внедренным выражениям.

Глобальные пространства имен XML следуют тем же правилам области и определения, что и .NET Framework пространства имен. В результате можно включить инструкцию `Imports`, чтобы определить глобальное пространство имен XML в любом месте, где можно импортировать пространство имен .NET Framework. Сюда входят файлы кода и импортированные пространства имен на уровне проекта. Сведения об импортированных пространствах имен на уровне проекта см. в разделе [Страница "ссылки" в конструкторе проектов (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).

Каждый исходный файл может содержать любое количество инструкций `Imports`. Они должны следовать объявлениям параметров, таким как оператор `Option Strict`, и должны предшествовать объявлениям элементов программирования, таким как `Module` или операторы `Class`.

## <a name="example"></a>Пример

В следующем примере выполняется импорт пространства имен XML по умолчанию и пространства имен XML, определенного префиксом `ns`. Затем он создает литералы XML, которые используют оба пространства имен.

[!code-vb[VbXMLSamples#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/Module1.vb#45)]

Этот пример кода отображает следующий текст:

```xml
<ns:outer xmlns="http://DefaultNamespace"
          xmlns:ns="http://NewNamespace">
  <ns:innerElement></ns:innerElement>
  <siblingElement></siblingElement>
  <innerElement />
</ns:outer>
```

## <a name="example"></a>Пример

В следующем примере выполняется импорт префикса пространства имен XML `ns`. Затем он создает XML-литерал, использующий префикс пространства имен, и отображает окончательную форму элемента.

[!code-vb[VbXMLSamples#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples10.vb#22)]

Этот пример кода отображает следующий текст:

```xml
<ns:outer xmlns:ns="http://SomeNamespace">
  <ns:middle xmlns:ns="http://NewNamespace">
    <ns:inner1 />
    <inner2 xmlns="http://SomeNamespace" />
  </ns:middle>
</ns:outer>
```

Обратите внимание, что компилятор преобразует префикс пространства имен XML из глобального префикса в локальное определение префикса.

## <a name="example"></a>Пример

В следующем примере выполняется импорт префикса пространства имен XML `ns`. Затем префикс пространства имен используется для создания литерала XML и доступа к первому дочернему узлу с полным именем `ns:name`.

[!code-vb[VbXMLSamples#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples8.vb#19)]

Этот пример кода отображает следующий текст:

`Patrick Hines`

## <a name="see-also"></a>См. также

- [XML-литерал элемента](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [Свойства оси XML](../../../visual-basic/language-reference/xml-axis/index.md)
- [Имена объявленных элементов и атрибутов XML](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
- [Оператор GetXmlNamespace](../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md)
