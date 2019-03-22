---
title: Практическое руководство. Использование индексированных свойств в программировании COM-взаимодействия (Руководство по программированию на C#)
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- indexed properties [C#]
- Office programming [C#], indexed properties
- properties [C#], indexed
ms.assetid: 756bfc1e-7c28-4d4d-b114-ac9288c73882
ms.openlocfilehash: 4b064f7042e5e5f0f6d5545c59de2f37897927b4
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56978037"
---
# <a name="how-to-use-indexed-properties-in-com-interop-programming-c-programming-guide"></a><span data-ttu-id="69c85-102">Практическое руководство. Использование индексированных свойств в программировании COM-взаимодействия (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="69c85-102">How to: Use Indexed Properties in COM Interop Programming (C# Programming Guide)</span></span>
<span data-ttu-id="69c85-103">*Индексированные свойства* делают использование свойств COM с параметрами при программировании на C# более удобным.</span><span class="sxs-lookup"><span data-stu-id="69c85-103">*Indexed properties* improve the way in which COM properties that have parameters are consumed in C# programming.</span></span> <span data-ttu-id="69c85-104">Индексированные свойства используются совместно с другими компонентами, представленными в Visual C#, например [именованными и необязательными аргументами](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md), новым типом ([dynamic](../../../csharp/language-reference/keywords/dynamic.md)) и [внедренными сведениями о типах](../../../csharp/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md) для расширения возможностей программирования для Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="69c85-104">Indexed properties work together with other features in Visual C#, such as [named and optional arguments](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md), a new type ([dynamic](../../../csharp/language-reference/keywords/dynamic.md)), and [embedded type information](../../../csharp/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md), to enhance Microsoft Office programming.</span></span>  
  
 <span data-ttu-id="69c85-105">В более ранних версиях C# методы доступны как свойства только при условии, что у метода `get` нет параметров, а у метода `set` есть только один параметр значения.</span><span class="sxs-lookup"><span data-stu-id="69c85-105">In earlier versions of C#, methods are accessible as properties only if the `get` method has no parameters and the `set` method has one and only one value parameter.</span></span> <span data-ttu-id="69c85-106">Однако не все свойства COM удовлетворяют этим ограничениям.</span><span class="sxs-lookup"><span data-stu-id="69c85-106">However, not all COM properties meet those restrictions.</span></span> <span data-ttu-id="69c85-107">Например, свойство <xref:Microsoft.Office.Interop.Excel.Range.Range%2A> Excel имеет метод доступа `get`, которому требуется параметр для имени диапазона.</span><span class="sxs-lookup"><span data-stu-id="69c85-107">For example, the Excel <xref:Microsoft.Office.Interop.Excel.Range.Range%2A> property has a `get` accessor that requires a parameter for the name of the range.</span></span> <span data-ttu-id="69c85-108">Раньше из-за отсутствия возможности прямого обращения к свойству `Range` приходилось использовать вместо этого метод `get_Range`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="69c85-108">In the past, because you could not access the `Range` property directly, you had to use the `get_Range` method instead, as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideIndexedProperties#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#1)]  
  
 <span data-ttu-id="69c85-109">Индексированные свойства позволяют вместо этого использовать следующий код:</span><span class="sxs-lookup"><span data-stu-id="69c85-109">Indexed properties enable you to write the following instead:</span></span>  
  
 [!code-csharp[csProgGuideIndexedProperties#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#2)]  
  
> [!NOTE]
>  <span data-ttu-id="69c85-110">В предыдущем примере также используются [необязательные аргументы](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md), которые позволяют опустить `Type.Missing`.</span><span class="sxs-lookup"><span data-stu-id="69c85-110">The previous example also uses the [optional arguments](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md) feature, which enables you to omit `Type.Missing`.</span></span>  
  
 <span data-ttu-id="69c85-111">Аналогичным образом, чтобы задать значение свойства `Value` объекта <xref:Microsoft.Office.Interop.Excel.Range> в Visual C# 2008 и более ранних версиях, требуется два аргумента.</span><span class="sxs-lookup"><span data-stu-id="69c85-111">Similarly to set the value of the `Value` property of a <xref:Microsoft.Office.Interop.Excel.Range> object in Visual C# 2008 and earlier, two arguments are required.</span></span> <span data-ttu-id="69c85-112">Один предоставляет аргумент для необязательного параметра, указывающего тип значения диапазона.</span><span class="sxs-lookup"><span data-stu-id="69c85-112">One supplies an argument for an optional parameter that specifies the type of the range value.</span></span> <span data-ttu-id="69c85-113">Другой предоставляет значение для свойства `Value`.</span><span class="sxs-lookup"><span data-stu-id="69c85-113">The other supplies the value for the `Value` property.</span></span> <span data-ttu-id="69c85-114">Эти методы показаны в следующих примерах.</span><span class="sxs-lookup"><span data-stu-id="69c85-114">The following examples illustrate these techniques.</span></span> <span data-ttu-id="69c85-115">В примерах ячейке A1 задается значение `Name`.</span><span class="sxs-lookup"><span data-stu-id="69c85-115">Both set the value of the A1 cell to `Name`.</span></span>
  
 [!code-csharp[csProgGuideIndexedProperties#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#3)]  
  
 <span data-ttu-id="69c85-116">Индексированные свойства позволяют вместо этого использовать следующий код.</span><span class="sxs-lookup"><span data-stu-id="69c85-116">Indexed properties enable you to write the following code instead.</span></span>  
  
 [!code-csharp[csProgGuideIndexedProperties#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#4)]  
  
 <span data-ttu-id="69c85-117">Разработчики не могут создавать собственные индексированные свойства.</span><span class="sxs-lookup"><span data-stu-id="69c85-117">You cannot create indexed properties of your own.</span></span> <span data-ttu-id="69c85-118">Эта возможность поддерживает только использование имеющихся индексированных свойств.</span><span class="sxs-lookup"><span data-stu-id="69c85-118">The feature only supports consumption of existing indexed properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="69c85-119">Пример</span><span class="sxs-lookup"><span data-stu-id="69c85-119">Example</span></span>  
 <span data-ttu-id="69c85-120">Ниже приведен полный пример кода.</span><span class="sxs-lookup"><span data-stu-id="69c85-120">The following code shows a complete example.</span></span> <span data-ttu-id="69c85-121">Дополнительные сведения о создании проекта, который обращается к Office API, см. в практическом руководстве по [ получению доступа к объектам взаимодействия Office с помощью функций Visual C#](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md).</span><span class="sxs-lookup"><span data-stu-id="69c85-121">For more information about how to set up a project that accesses the Office API, see [How to: Access Office Interop Objects by Using Visual C# Features](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md).</span></span>  
  
 [!code-csharp[csProgGuideIndexedProperties#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#5)]  
  
## <a name="see-also"></a><span data-ttu-id="69c85-122">См. также</span><span class="sxs-lookup"><span data-stu-id="69c85-122">See also</span></span>

- [<span data-ttu-id="69c85-123">Именованные и необязательные аргументы</span><span class="sxs-lookup"><span data-stu-id="69c85-123">Named and Optional Arguments</span></span>](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md)
- [<span data-ttu-id="69c85-124">dynamic</span><span class="sxs-lookup"><span data-stu-id="69c85-124">dynamic</span></span>](../../../csharp/language-reference/keywords/dynamic.md)
- [<span data-ttu-id="69c85-125">Использование типа dynamic</span><span class="sxs-lookup"><span data-stu-id="69c85-125">Using Type dynamic</span></span>](../../../csharp/programming-guide/types/using-type-dynamic.md)
- [<span data-ttu-id="69c85-126">Практическое руководство. Использование именованных и необязательных аргументов в программировании приложений Office</span><span class="sxs-lookup"><span data-stu-id="69c85-126">How to: Use Named and Optional Arguments in Office Programming</span></span>](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md)
- [<span data-ttu-id="69c85-127">Практическое руководство. Доступ к объектам взаимодействия Office с помощью функций языка Visual C#</span><span class="sxs-lookup"><span data-stu-id="69c85-127">How to: Access Office Interop Objects by Using Visual C# Features</span></span>](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md)
- [<span data-ttu-id="69c85-128">Пошаговое руководство: Программирование для Office</span><span class="sxs-lookup"><span data-stu-id="69c85-128">Walkthrough: Office Programming</span></span>](../../../csharp/programming-guide/interop/walkthrough-office-programming.md)
