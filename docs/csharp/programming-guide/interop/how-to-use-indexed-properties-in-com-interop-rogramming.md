---
title: Практическое руководство. Использование индексированных свойств в программировании COM-взаимодействия (Руководство по программированию на C#)
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- indexed properties [C#]
- Office programming [C#], indexed properties
- properties [C#], indexed
ms.assetid: 756bfc1e-7c28-4d4d-b114-ac9288c73882
ms.openlocfilehash: 0d4e85646a1e7f8c4ee9a73fbf7bf5a01b10b14b
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423222"
---
# <a name="how-to-use-indexed-properties-in-com-interop-programming-c-programming-guide"></a>Практическое руководство. Использование индексированных свойств в программировании COM-взаимодействия (Руководство по программированию на C#)
*Индексированные свойства* делают использование свойств COM с параметрами при программировании на C# более удобным. Индексированные свойства используются совместно с другими компонентами, представленными в Visual C#, например [именованными и необязательными аргументами](../classes-and-structs/named-and-optional-arguments.md), новым типом ([dynamic](../../language-reference/builtin-types/reference-types.md)) и [внедренными сведениями о типах](../../../standard/assembly/embed-types-visual-studio.md) для расширения возможностей программирования для Microsoft Office.  
  
 В более ранних версиях C# методы доступны как свойства только при условии, что у метода `get` нет параметров, а у метода `set` есть только один параметр значения. Однако не все свойства COM удовлетворяют этим ограничениям. Например, свойство <xref:Microsoft.Office.Interop.Excel.Range.Range%2A> Excel имеет метод доступа `get`, которому требуется параметр для имени диапазона. Раньше из-за отсутствия возможности прямого обращения к свойству `Range` приходилось использовать вместо этого метод `get_Range`, как показано в следующем примере.  
  
 [!code-csharp[csProgGuideIndexedProperties#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#1)]  
  
 Индексированные свойства позволяют вместо этого использовать следующий код:  
  
 [!code-csharp[csProgGuideIndexedProperties#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#2)]  
  
> [!NOTE]
> В предыдущем примере также используются [необязательные аргументы](../classes-and-structs/named-and-optional-arguments.md), которые позволяют опустить `Type.Missing`.  
  
 Аналогичным образом, чтобы задать значение свойства `Value` объекта <xref:Microsoft.Office.Interop.Excel.Range> в C# 3.0 и более ранних версиях, требуются два аргумента. Один предоставляет аргумент для необязательного параметра, указывающего тип значения диапазона. Другой предоставляет значение для свойства `Value`. Эти методы показаны в следующих примерах. В примерах ячейке A1 задается значение `Name`.
  
 [!code-csharp[csProgGuideIndexedProperties#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#3)]  
  
 Индексированные свойства позволяют вместо этого использовать следующий код.  
  
 [!code-csharp[csProgGuideIndexedProperties#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#4)]  
  
 Разработчики не могут создавать собственные индексированные свойства. Эта возможность поддерживает только использование имеющихся индексированных свойств.  
  
## <a name="example"></a>Пример  
 Ниже приведен полный пример кода. Дополнительные сведения о создании проекта, который обращается к Office API, см. в практическом руководстве по [ получению доступа к объектам взаимодействия Office с помощью функций Visual C#](./how-to-access-office-onterop-objects.md).  
  
 [!code-csharp[csProgGuideIndexedProperties#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#5)]  
  
## <a name="see-also"></a>См. также

- [Именованные и необязательные аргументы](../classes-and-structs/named-and-optional-arguments.md)
- [dynamic](../../language-reference/builtin-types/reference-types.md)
- [Использование типа dynamic](../types/using-type-dynamic.md)
- [Практическое руководство. Использование именованных и необязательных аргументов в программировании приложений Office](../classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md)
- [Практическое руководство. Доступ к объектам взаимодействия Office с помощью функций языка Visual C#](./how-to-access-office-onterop-objects.md)
- [Пошаговое руководство: Программирование для Office](./walkthrough-office-programming.md)
