---
title: "Оператор Imports (пространство имен XML) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.ImportsXmlns"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "импорт [Visual Basic]"
  - "Imports - оператор [Visual Basic]"
  - "пространства имен [Visual Basic], импорт"
  - "XML-пространства имен [Visual Basic], импорт"
ms.assetid: 1f4d50a6-08c7-4c2e-8206-ccae35fcd1b4
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Оператор Imports (пространство имен XML)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Импортирует префиксы пространства имен XML для использования в XML\-литералах и свойствах оси XML.  
  
## Синтаксис  
  
```  
Imports <xmlns:xmlNamespacePrefix = "xmlNamespaceName">  
```  
  
## Части  
 `xmlNamespacePrefix`  
 Необязательный.  Строка, с помощью которой элементы и атрибуты XML могут ссылаться на пространство имен `xmlNamespaceName`.  Если пространство имен `xmlNamespacePrefix` не указано, в качестве импортированного используется пространство имен XML по умолчанию.  Должен являться допустимым XML\-идентификатором.  Дополнительные сведения см. в разделе [Имена объявляемых элементов и атрибутов XML](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).  
  
 `xmlNamespaceName`  
 Обязательный.  Строка, идентифицирующая импортируемое пространство имен XML.  
  
## Заметки  
 Оператор `Imports` можно использовать для определения глобальных пространств имен XML, которые можно использовать с XML\-литералами и свойствами оси XML, или как параметры, переданные оператору `GetXmlNamespace`.  \(Сведения об использовании оператора `Imports` для импорта псевдонимов, которые могут быть использованы в коде там, где используются имена типов, см. в разделе [Оператор Imports \(пространство имен .NET и тип\)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).\) Синтаксис объявления пространства имен XML с помощью инструкции `Imports` идентичен синтаксису, используемому в формате XML.  Таким образом, можно скопировать объявление пространства имен из XML\-файла и использовать его в операторе `Imports`.  
  
 Префиксы пространства имен XML полезны, если требуется повторно создать XML\-элементы, принадлежащие одному пространству имен.  Префикс пространства имен XML, объявляемый с использованием оператора `Imports`, является глобальным и доступен всему коду в файле.  Его можно использовать при создании литерала XML\-элемента и при доступе к свойствам оси XML.  Дополнительные сведения см. в разделах [Литеральное представление XML\-элемента](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) и [Свойства оси XML](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md).  
  
 Если определить глобальное пространство имен XML без префикса пространства имен \(например `Imports <xmlns="http://SomeNameSpace>"`\), такое пространство рассматривается как пространство имен XML по умолчанию.  Пространство имен XML по умолчанию используется для любых литералов XML\-элемента или свойств оси XML\-атрибутов, для которых явно не указано пространство имен.  Пространство имен по умолчанию также используется при указании пустого пространства имен \(то есть `xmlns=""`\).  Пространство имен XML по умолчанию не применяется для XML\-атрибутов или для свойств осей XML\-литералов, не имеющих пространства имен.  
  
 Пространства имен XML, определенные в XML\-литерале \(называются *локальными пространствами имен XML*\), имеют приоритет над пространствами имен XML, определенными как глобальные с помощью оператора `Imports`.  Пространства имен XML, определенные с помощью оператора `Imports`, имеют приоритет над пространствами имен XML, импортированными в проект Visual Basic.  Если XML\-литерал определяет пространство имен XML, то локальное пространство имен неприменимо к внедренным выражениям.  
  
 Глобальное пространство имен XML следует тем же самым правилам определения, что и пространство имен .NET Framework, и имеет ту же область действия.  В результате можно включить оператор `Imports` для определения глобального пространства имен XML везде, где можно импортировать пространство имен .NET Framework.  Это включает файлы кода и импортированные на уровне проекта пространства имен.  Сведения о пространствах имен уровня проекта см. в разделе [Страница "Ссылки" в конструкторе проектов \(Visual Basic\)](/visual-studio/ide/reference/references-page-project-designer-visual-basic).  
  
 Каждый исходный файл может содержать любое количество операторов `Imports`.  Они должны следовать за параметром объявления, например оператором `Option Strict`, и предшествовать объявлению элементов программированию, например операторам `Module` или `Class`.  
  
## Пример  
 В следующем примере производится импорт пространства имен XML по умолчанию и пространства имен XML, определенного с префиксом `ns`.  Затем создаются XML\-литералы, использующие оба пространства имен.  
  
 [!code-vb[VbXMLSamples#45](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_1.vb)]  
  
 В этом коде отображается следующий текст:  
  
```  
<ns:outer xmlns="http://DefaultNamespace"   
          xmlns:ns="http://NewNamespace">  
  <ns:innerElement></ns:innerElement>  
  <siblingElement></siblingElement>  
  <innerElement />  
</ns:outer>  
```  
  
## Пример  
 В следующем примере импортируется префикс пространства имен XML `ns`.  Затем создается XML\-литерал, который использует префикс пространства имен, и отображается конечная форма элемента.  
  
 [!code-vb[VbXMLSamples#22](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_2.vb)]  
  
 В этом коде отображается следующий текст:  
  
```  
<ns:outer xmlns:ns="http://SomeNamespace">  
  <ns:middle xmlns:ns="http://NewNamespace">  
    <ns:inner1 />  
    <inner2 xmlns="http://SomeNamespace" />  
  </ns:middle>  
</ns:outer>  
```  
  
 Обратите внимание, что компилятор преобразует префикс из глобального префикса в определение локального префикса пространства имен XML.  
  
## Пример  
 В следующем примере импортируется префикс пространства имен XML `ns`.  Затем используется префикс пространства имен для создания XML\-литерала и доступа к первому дочернему узлу, имеющему полное имя `ns:name`.  
  
 [!code-vb[VbXMLSamples#19](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_3.vb)]  
  
 В этом коде отображается следующий текст:  
  
 `Patrick Hines`  
  
## См. также  
 [Литеральное представление XML\-элемента](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)   
 [Свойства оси XML](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)   
 [Имена объявляемых элементов и атрибутов XML](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)   
 [Оператор GetXmlNamespace](../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md)