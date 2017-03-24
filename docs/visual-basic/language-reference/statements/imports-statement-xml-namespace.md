---
title: "Оператор Imports (пространство имен XML) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.ImportsXmlns
dev_langs:
- VB
helpviewer_keywords:
- XML namespace [Visual Basic], importing
- imports [Visual Basic]
- Imports statement [Visual Basic]
- namespaces [Visual Basic], importing
ms.assetid: 1f4d50a6-08c7-4c2e-8206-ccae35fcd1b4
caps.latest.revision: 18
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: 546168994973d19336f86f4b4e9ec566f0b9dd91
ms.lasthandoff: 03/13/2017

---
# <a name="imports-statement-xml-namespace"></a>Оператор Imports (пространство имен XML)
Импортирует префиксы пространства имен XML для использования в XML-литералы и свойства оси XML.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Imports <xmlns:xmlNamespacePrefix = "xmlNamespaceName">  
```  
  
## <a name="parts"></a>Части  
 `xmlNamespacePrefix`  
 Необязательный. Строка, по которой XML элементы и атрибуты можно обращаться к `xmlNamespaceName`. Если не `xmlNamespacePrefix` будет указано, импортируемое пространство имен XML — пространство имен XML по умолчанию. Должен быть допустимым идентификатором XML. Дополнительные сведения см. в разделе [имена объявленных элементов XML и атрибутов](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).  
  
 `xmlNamespaceName`  
 Обязательный. Строка, определяющая импортируемого пространства имен XML.  
  
## <a name="remarks"></a>Примечания  
 Можно использовать `Imports` инструкции для определения глобального пространства имен XML, который можно использовать с XML-литералы и свойства оси XML, а также параметры, передаваемые `GetXmlNamespace` оператор. (Дополнительные сведения об использовании `Imports` statement, чтобы импортировать псевдоним, который можно использовать, где используются имена типов в коде, в разделе [оператор Imports (пространство имен .NET и тип)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).) Синтаксис объявления пространства имен XML с помощью `Imports` инструкции идентичен синтаксису, используемому в формате XML. Таким образом, можно скопировать объявление пространства имен из XML-файла и использовать его в `Imports` инструкции.  
  
 Префиксы пространства имен XML полезны, когда требуется повторно создать элементы XML, которые находятся в том же пространстве имен. Префикс пространства имен XML, объявленные с `Imports` инструкция является глобальным в том смысле, что он доступен всему коду в файле. Его можно использовать при создании литералов XML-элемента и при доступе к свойствам осей XML. Дополнительные сведения см. в разделе [литерала XML элемент](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) и [свойства оси XML](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md).  
  
 Если можно определить глобальное пространство имен XML без префикса пространства имен (например, `Imports <xmlns="http://SomeNameSpace>"`), такое пространство рассматривается как пространство имен XML по умолчанию. Пространство имен XML по умолчанию используется для любого элемента XML-литералов или свойств оси атрибута XML, которых явно не указано пространство имен. Пространство имен по умолчанию также используется, если указанного пространства имен является пустое пространство имен (то есть, `xmlns=""`). Пространство имен XML по умолчанию не применяется для атрибутов XML в XML-литералов или свойства оси атрибута XML, у которых нет пространства имен.  
  
 Пространства имен XML, определенные в XML-литерал, который называются *локальными пространствами имен XML*, имеют приоритет над пространствами имен XML, определяются `Imports` инструкции в качестве глобальных. Пространства имен XML, который определен с `Imports` инструкции имеют приоритет над пространствами имен XML, импортированные для проекта Visual Basic. Если XML-литерал определяет пространство имен XML, то Локальное пространство имен неприменимо к внедренные выражения.  
  
 Глобальные пространства имен XML, выполните те же правила области видимости и определения пространства имен .NET Framework. В результате можно включить `Imports` инструкции для определения глобального пространства имен XML в любом месте можно импортировать пространство имен .NET Framework. Это включает файлы кода и импортированные пространства имен на уровне проекта. Сведения о пространствах имен уровня проекта см. в разделе [страница "ссылки" в конструкторе проектов (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic).  
  
 Каждый исходный файл может содержать любое количество `Imports` инструкции. Они должны следовать за параметром объявления, такие как `Option Strict` инструкции и они должны предшествовать объявления элементов программирования, таких как `Module` или `Class` инструкции.  
  
## <a name="example"></a>Пример  
 В следующем примере импортируется пространство имен XML по умолчанию и определить префикс пространства имен XML `ns`. Затем он создает XML-литералы, использующие оба пространства имен.  
  
 [!code-vb[VbXMLSamples&#45;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_1.vb)]  
  
 Этот пример кода отображает следующий текст:  
  
```  
<ns:outer xmlns="http://DefaultNamespace"   
          xmlns:ns="http://NewNamespace">  
  <ns:innerElement></ns:innerElement>  
  <siblingElement></siblingElement>  
  <innerElement />  
</ns:outer>  
```  
  
## <a name="example"></a>Пример  
 В следующем примере импортируется префикс пространства имен XML `ns`. Затем он создает XML-литерал, использует префикс пространства имен и отображается конечная форма элемента.  
  
 [!code-vb[VbXMLSamples&#22;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_2.vb)]  
  
 Этот пример кода отображает следующий текст:  
  
```  
<ns:outer xmlns:ns="http://SomeNamespace">  
  <ns:middle xmlns:ns="http://NewNamespace">  
    <ns:inner1 />  
    <inner2 xmlns="http://SomeNamespace" />  
  </ns:middle>  
</ns:outer>  
```  
  
 Обратите внимание, что компилятор преобразует префикс пространства имен XML из глобального префикса в определение локального префикса.  
  
## <a name="example"></a>Пример  
 В следующем примере импортируется префикс пространства имен XML `ns`. Затем префикс пространства имен используется для создания литерала XML и доступа к первому дочернему узлу с полным именем `ns:name`.  
  
 [!code-vb[VbXMLSamples&19;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_3.vb)]  
  
 Этот пример кода отображает следующий текст:  
  
 `Patrick Hines`  
  
## <a name="see-also"></a>См. также  
 [Литеральное представление XML элемента](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)   
 [Свойства оси XML](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)   
 [Имена объявленных элементов и атрибутов](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)   
 [Оператор GetXmlNamespace](../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md)
