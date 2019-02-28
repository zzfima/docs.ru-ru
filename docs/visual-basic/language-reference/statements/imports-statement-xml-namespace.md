---
title: Оператор - Imports пространство имен XML (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ImportsXmlns
helpviewer_keywords:
- XML namespace [Visual Basic], importing
- imports [Visual Basic]
- Imports statement [Visual Basic]
- namespaces [Visual Basic], importing
ms.assetid: 1f4d50a6-08c7-4c2e-8206-ccae35fcd1b4
ms.openlocfilehash: 8cce1cc918b150fdf30449f127b1e2f0a73e6f6c
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56973279"
---
# <a name="imports-statement-xml-namespace"></a>Оператор Imports (пространство имен XML)
Импортирует префиксы пространства имен XML для использования в XML-литералы и свойства оси XML.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Imports <xmlns:xmlNamespacePrefix = "xmlNamespaceName">  
```  
  
## <a name="parts"></a>Части  
 `xmlNamespacePrefix`  
 Необязательный параметр. Строка, по котором XML элементы и атрибуты можно обращаться к `xmlNamespaceName`. Если нет `xmlNamespacePrefix` будет указано, импортируемое пространство имен XML — это пространство имен XML по умолчанию. Должен быть допустимым идентификатором XML. Дополнительные сведения см. в разделе [имена объявленных элементов XML и атрибутов](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).  
  
 `xmlNamespaceName`  
 Обязательный. Строка, идентифицирующая импортируемого пространства имен XML.  
  
## <a name="remarks"></a>Примечания  
 Можно использовать `Imports` инструкции для определения глобальных пространств имен XML, который можно использовать с XML-литералы и свойства оси XML, или в качестве параметров, переданных `GetXmlNamespace` оператор. (Дополнительные сведения об использовании `Imports` инструкцию, чтобы импортировать псевдоним, который может использоваться где имена типов используются в коде, см. в разделе [оператор Imports (пространство имен .NET и тип)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).) Синтаксис объявления пространства имен XML с помощью `Imports` инструкция идентична синтаксисе, используемом в XML. Таким образом, можно скопировать объявление пространства имен из файла XML и использовать его в `Imports` инструкции.  
  
 Префиксы пространства имен XML полезны в тех случаях, когда вы хотите повторно создать XML-элементах из одного пространства имен. Префикс пространства имен XML объявлен с `Imports` инструкция является глобальным в том смысле, что он доступен на весь код в файле. Его можно использовать при создании литералов XML-элемента и при доступе к свойства оси XML. Дополнительные сведения см. в разделе [литерала элемента XML](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) и [свойства оси XML](../../../visual-basic/language-reference/xml-axis/index.md).  
  
 Если можно определить глобальное пространство имен XML без префикса пространства имен (например, `Imports <xmlns="http://SomeNameSpace>"`), это пространство имен считается пространство имен XML по умолчанию. Для любого элемента XML-литералов или свойств оси атрибута XML пространство имен явно не указано, используется пространство имен XML по умолчанию. Пространство имен по умолчанию используется также в том случае, если указанное пространство имен является пустое пространство имен (то есть `xmlns=""`). Пространство имен XML по умолчанию не применяется к атрибутам XML в XML-литералов или свойств оси атрибута XML, у которых нет пространства имен.  
  
 Пространства имен XML, определенные в XML-литерал, которые называются *локального пространства имен XML*, имеют приоритет над пространств имен XML, которые определяются `Imports` инструкцию как глобальный. Пространства имен XML, которые определяются `Imports` инструкции имеют приоритет над пространства имен XML, импортированные в проекте Visual Basic. Если XML-литерал определяет пространство имен XML, то Локальное пространство имен не применяется к внедренные выражения.  
  
 Глобальные пространства имен XML, выполните те же правила области видимости и определения пространства имен .NET Framework. Таким образом, можно включить `Imports` инструкции для определения глобального пространства имен XML в любом месте, вы можете импортировать пространство имен .NET Framework. Сюда входят файлы кода и импортированных пространств имен уровня проекта. Сведения о пространствах имен уровня проекта, см. в разделе [страница "ссылки", конструктор проектов (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).  
  
 Каждый исходный файл может содержать любое количество `Imports` инструкций. Они должны следовать за параметром объявления, такие как `Option Strict` инструкции и они должны указываться до объявлений элементов программирования, таких как `Module` или `Class` инструкций.  
  
## <a name="example"></a>Пример  
 В следующем примере импортируется в пространство имен XML по умолчанию и идентифицировать с помощью префикса пространства имен XML `ns`. Затем он создает XML-литералов, использующих обоих пространствах имен.  
  
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
 В следующем примере выполняется импорт префикс пространства имен XML `ns`. Затем он создает XML-литерала, использует префикс пространства имен и отображает окончательной форме этого элемента.  
  
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
  
 Обратите внимание на то, что компилятор преобразует префикс пространства имен XML из глобального префикса определение локального префикса.  
  
## <a name="example"></a>Пример  
 В следующем примере выполняется импорт префикс пространства имен XML `ns`. Затем префикс пространства имен используется для создания литерала XML и доступа к первому дочернему узлу с полным именем `ns:name`.  
  
 [!code-vb[VbXMLSamples#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples8.vb#19)]  
  
 Этот пример кода отображает следующий текст:  
  
 `Patrick Hines`  
  
## <a name="see-also"></a>См. также
- [XML-литерал элемента](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [Свойства оси XML](../../../visual-basic/language-reference/xml-axis/index.md)
- [Имена объявленных элементов и атрибутов XML](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
- [Оператор GetXmlNamespace](../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md)
