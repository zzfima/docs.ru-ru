---
title: "Escape-последовательности {} - расширение разметки"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: '{}'
helpviewer_keywords:
- XAML [XAML Services], quotation mark (")
- '{} escape sequence [XAML Services]'
- XAML [XAML Services], {} escape sequence
- XAML [XAML Services], escape sequence
- quotation mark (") [XAML Services]
- escape sequence [XAML Services]
ms.assetid: 3ce3e2ad-a868-43f9-9c98-b29561cb146e
caps.latest.revision: "21"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8419a1e89d5e94b9868b0fd1fb81540253efca5d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="-escape-sequence--markup-extension"></a>Escape-последовательность/расширение разметки {}
Предоставляет escape-последовательности XAML для значений атрибутов. Escape-последовательности позволяет последующие значения в атрибуте интерпретироваться как литерал.  
  
## <a name="xaml-attribute-usage"></a>Использование атрибута XAML  
  
```xml  
<object property="{} literalValue" .../>  
```  
  
## <a name="xaml-property-element-usage"></a>Использование элемента свойства XAML  
  
```  
<object>  
  <object.property>  
    {} literalValue  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a>Значения XAML  
  
|||  
|-|-|  
|*literalValue*|Символьная строка соответствует escape-последовательность. Обычно эта строка содержит открытия или закрытия фигурной скобки ({и}).|  
  
## <a name="remarks"></a>Примечания  
 Escape-последовательность ({}) используется, чтобы открывающая фигурная скобка ({}), которые можно использовать как буквенный символ в XAML.  
  
 Средства чтения XAML обычно используется открывающая фигурная скобка ({}) для обозначения точки входа расширения разметки; Однако они сначала проверьте следующий символ, чтобы определить, является ли закрывающей фигурной скобкой (}). Только в том случае, если две фигурные скобки ({}) являются смежными, они считаются escape-последовательность.  
  
 При обнаружении escape-последовательность средство чтения XAML должен обработать остаток строки как строка. Тем не менее если escape-последовательность применяется к члену, который преобразователь типа, строка может претерпеть преобразование типов, когда он интерпретируется модулем записи XAML.  
  
 Escape-последовательность не является расширением разметки и не поддерживается классом. Однако это соглашение, которое следует использовать средства чтения XAML (включая пользовательские модули чтения XAML).  
  
 Знак кавычек ("") не может использоваться как escape-последовательность таким образом. Если необходимо задать знак кавычек в качестве значения свойства для свойства, не являющегося содержимым, используйте синтаксис элемента свойства и поместите знак кавычки в виде строки внутри элемента свойства или используйте сущность символов XML. Для свойства содержимого знак кавычки можно всего содержимого.  
  
 Escape-последовательность ({}) часто используется при указании типа XML, который должен включать квалификатор пространства имен в месте, где может отображаться расширение разметки XAML. Это включает запуск из значений атрибутов XAML, а также в расширении разметки, сразу после знака равенства (=). В следующем примере показано escape-последовательности для пространства имен XML, который появляется в начале значения атрибута XAML.  
  
 [!code-xaml[XLINQExample#StackPanelResources](../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]  
  
## <a name="see-also"></a>См. также  
 [Преобразователи типов или расширения разметки для XAML](../../../docs/framework/xaml-services/type-converters-and-markup-extensions-for-xaml.md)  
 [Сущности знаков XML и XAML](../../../docs/framework/xaml-services/xml-character-entities-and-xaml.md)
