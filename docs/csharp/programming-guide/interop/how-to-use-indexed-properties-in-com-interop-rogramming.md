---
title: "Практическое руководство. Использование индексированных свойств в программировании COM-взаимодействия (Руководство по программированию на C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- indexed properties [C#]
- Office programming [C#], indexed properties
- properties [C#], indexed
ms.assetid: 756bfc1e-7c28-4d4d-b114-ac9288c73882
caps.latest.revision: "20"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 6ccd4248730d3c89528dad62b3f8ced3b9e42b0f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-indexed-properties-in-com-interop-programming-c-programming-guide"></a>Практическое руководство. Использование индексированных свойств в программировании COM-взаимодействия (Руководство по программированию на C#)
*Индексированные свойства* делают использование свойств COM с параметрами при программировании на C# более удобным. Индексированные свойства используются совместно с другими компонентами, представленными в Visual C#, например [именованными и необязательными аргументами](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md), новым типом ([dynamic](../../../csharp/language-reference/keywords/dynamic.md)) и [внедренными сведениями о типах](../../../csharp/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md) для расширения возможностей программирования для Microsoft Office.  
  
 В более ранних версиях C# методы доступны как свойства только при условии, что у метода `get` нет параметров, а у метода `set` есть только один параметр значения. Однако не все свойства COM удовлетворяют этим ограничениям. Например, свойство [Range](http://go.microsoft.com/fwlink/?LinkId=166053) Excel имеет метод доступа `get`, которому требуется параметр для имени диапазона. Раньше из-за отсутствия возможности прямого обращения к свойству `Range` приходилось использовать вместо этого метод `get_Range`, как показано в следующем примере.  
  
 [!code-csharp[csProgGuideIndexedProperties#1](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_1.cs)]  
  
 Индексированные свойства позволяют вместо этого использовать следующий код:  
  
 [!code-csharp[csProgGuideIndexedProperties#2](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_2.cs)]  
  
> [!NOTE]
>  В предыдущем примере также используются [необязательные аргументы](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md), которые позволяют опустить `Type.Missing`.  
  
 Аналогичным образом, чтобы задать значение свойства `Value` объекта [Range](https://msdn.microsoft.com/library/microsoft.office.interop.excel.range.aspx) в Visual C# 2008 и более ранних версиях, требуется два аргумента. Один предоставляет аргумент для необязательного параметра, указывающего тип значения диапазона. Другой предоставляет значение для свойства `Value`. Эти методы показаны в следующих примерах. В примерах ячейке A1 задается значение `Name`.
  
 [!code-csharp[csProgGuideIndexedProperties#3](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_3.cs)]  
  
 Индексированные свойства позволяют вместо этого использовать следующий код.  
  
 [!code-csharp[csProgGuideIndexedProperties#4](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_4.cs)]  
  
 Разработчики не могут создавать собственные индексированные свойства. Эта возможность поддерживает только использование имеющихся индексированных свойств.  
  
## <a name="example"></a>Пример  
 Ниже приведен полный пример кода. Дополнительные сведения о создании проекта, обращающегося к Office API, см. в разделе [Практическое руководство. Доступ к объектам взаимодействия Office с помощью функций языка Visual C#](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md).  
  
 [!code-csharp[csProgGuideIndexedProperties#5](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_5.cs)]  
  
## <a name="see-also"></a>См. также  
 [Именованные и необязательные аргументы](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md)  
 [dynamic](../../../csharp/language-reference/keywords/dynamic.md)  
 [Использование типа dynamic](../../../csharp/programming-guide/types/using-type-dynamic.md)  
 [Практическое руководство. Использование именованных и необязательных аргументов в программировании приложений Office](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md)  
 [Практическое руководство. Доступ к объектам взаимодействия Office с помощью функций языка Visual C# 2010](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md)  
 [Walkthrough: Office Programming](../../../csharp/programming-guide/interop/walkthrough-office-programming.md) (Пошаговое руководство. Программирование приложений Office)
