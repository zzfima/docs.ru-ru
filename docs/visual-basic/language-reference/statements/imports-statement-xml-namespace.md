---
title: Оператор Imports (пространство имен XML)
ms.date: 07/20/2015
f1_keywords:
- vb.ImportsXmlns
helpviewer_keywords:
- XML namespace [Visual Basic], importing
- imports [Visual Basic]
- Imports statement [Visual Basic]
- namespaces [Visual Basic], importing
ms.assetid: 1f4d50a6-08c7-4c2e-8206-ccae35fcd1b4
ms.openlocfilehash: ba7475416d8a4e2eb3c892d457c03eeb695045eb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="imports-statement-xml-namespace"></a>Оператор Imports (пространство имен XML)
Импортирует префиксы пространства имен XML для использования в XML-литералы и свойства оси XML.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Imports <xmlns:xmlNamespacePrefix = "xmlNamespaceName">  
```  
  
## <a name="parts"></a>Части  
 `xmlNamespacePrefix`  
 Необязательный. Строка, в котором XML элементы и атрибуты могут ссылаться на `xmlNamespaceName`. Если не `xmlNamespacePrefix` будет указано, импортируемое пространство имен XML — пространство имен XML по умолчанию. Должен быть допустимым идентификатором XML. Дополнительные сведения см. в разделе [имена из объявленных элементов и атрибутов XML](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).  
  
 `xmlNamespaceName`  
 Обязательно. Строка, определяющая импортируемого пространства имен XML.  
  
## <a name="remarks"></a>Примечания  
 Можно использовать `Imports` инструкции для определения глобальных пространств имен XML, который можно использовать с XML-литералы и свойства оси XML, или в качестве параметров, переданных `GetXmlNamespace` оператор. (Дополнительные сведения об использовании `Imports` инструкцию, чтобы импортировать псевдоним, который можно использовать, где используются имена типов в коде, в разделе [оператор Imports (пространство имен .NET и тип)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).) Синтаксис объявления пространства имен XML с помощью `Imports` инструкции идентична синтаксис, используемый в формате XML. Таким образом, можно скопировать объявление пространства имен из XML-файла и использовать его в `Imports` инструкции.  
  
 Префиксы пространства имен XML полезны в тех случаях, когда требуется повторно создать XML-элементах из одного пространства имен. Объявленный префикс пространства имен XML с `Imports` инструкция является глобальным в том смысле, что он доступен для всего кода в файле. Его можно использовать при создании литералов XML-элемента и при доступе к свойства оси XML. Дополнительные сведения см. в разделе [литерала элемента XML](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) и [свойства оси XML](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md).  
  
 Если определить глобальное пространство имен XML без префикса пространства имен (например, `Imports <xmlns="http://SomeNameSpace>"`), это пространство имен, считается пространства имен XML по умолчанию. Для любого элемента XML-литералов или свойств оси атрибута XML, не указывается пространство имен явно используется пространство имен XML по умолчанию. Пространство имен по умолчанию используется также в том случае, если указанное пространство имен является пустое пространство (то есть, `xmlns=""`). Пространство имен XML по умолчанию не применяется для атрибутов XML в XML-литералов или свойств оси атрибута XML, не имеет пространства имен.  
  
 Пространства имен XML, определенные в XML-литерал, которые называются *локального пространства имен XML*, имеют приоритет над пространствами имен XML, который определен с `Imports` инструкции как глобальный. Пространства имен XML, который определен с `Imports` инструкции имеют приоритет над пространства имен XML, импортированные в проекте Visual Basic. Если XML-литерал определяет пространство имен XML, то Локальное пространство имен не применяется к внедренные выражения.  
  
 Глобальные пространства имен XML подчиняются тем же правилам определения областей и определения, как пространства имен .NET Framework. В результате можно включить `Imports` инструкции для определения глобального пространства имен XML в любом месте можно импортировать пространство имен .NET Framework. Сюда входят файлы кода и импортированных пространств имен уровня проекта. Сведения о пространствах имен уровня проекта см. в разделе [страница "ссылки" в конструкторе проектов (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).  
  
 Каждый исходный файл может содержать любое количество `Imports` инструкции. Они должны следовать за параметром объявления, такие как `Option Strict` инструкции и они должны предшествовать объявлениям элементов программирования, таких как `Module` или `Class` инструкции.  
  
## <a name="example"></a>Пример  
 В следующем примере импортируется пространство имен XML по умолчанию и пространства имен XML, определенного с префиксом `ns`. Затем он создает XML-литералы, использующие оба пространства имен.  
  
 [!code-vb[VbXMLSamples#45](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_1.vb)]  
  
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
 В следующем примере выполняется импорт префикс пространства имен XML `ns`. Затем он создает XML-литерал, использует префикс пространства имен и отображается конечная форма элемента.  
  
 [!code-vb[VbXMLSamples#22](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_2.vb)]  
  
 Этот пример кода отображает следующий текст:  
  
```xml  
<ns:outer xmlns:ns="http://SomeNamespace">  
  <ns:middle xmlns:ns="http://NewNamespace">  
    <ns:inner1 />  
    <inner2 xmlns="http://SomeNamespace" />  
  </ns:middle>  
</ns:outer>  
```  
  
 Обратите внимание, что компилятор преобразует префикс пространства имен XML из глобального префикса определение локального префикса.  
  
## <a name="example"></a>Пример  
 В следующем примере выполняется импорт префикс пространства имен XML `ns`. Затем префикс пространства имен используется для создания литерала XML и доступа к первому дочернему узлу с полным именем `ns:name`.  
  
 [!code-vb[VbXMLSamples#19](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_3.vb)]  
  
 Этот пример кода отображает следующий текст:  
  
 `Patrick Hines`  
  
## <a name="see-also"></a>См. также  
 [XML-литерал элемента](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [Свойства оси XML](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 [Имена объявленных элементов и атрибутов XML](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)  
 [Оператор GetXmlNamespace](../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md)
