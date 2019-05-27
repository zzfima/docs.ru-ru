---
title: Отладка деревьев выражений в Visual Studio (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 492cc28f-b7a2-4c47-b582-b3c437b8a5d5
ms.openlocfilehash: 9aead09e0e9469f13e2d6befbad444d3c7fecabd
ms.sourcegitcommit: 96543603ae29bc05cecccb8667974d058af63b4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/24/2019
ms.locfileid: "66196025"
---
# <a name="debugging-expression-trees-in-visual-studio-visual-basic"></a><span data-ttu-id="99fdc-102">Отладка деревьев выражений в Visual Studio (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="99fdc-102">Debugging Expression Trees in Visual Studio (Visual Basic)</span></span>
<span data-ttu-id="99fdc-103">При отладке приложений можно анализировать структуру и содержимое деревьев выражений.</span><span class="sxs-lookup"><span data-stu-id="99fdc-103">You can analyze the structure and content of expression trees when you debug your applications.</span></span> <span data-ttu-id="99fdc-104">Чтобы получить краткий обзор структуры дерева выражения, можно использовать `DebugView` свойства, которое представляет деревьев выражений [с помощью специального синтаксиса](debugview-syntax.md).</span><span class="sxs-lookup"><span data-stu-id="99fdc-104">To get a quick overview of the expression tree structure, you can use the `DebugView` property, which represents expression trees [using a special syntax](debugview-syntax.md).</span></span> <span data-ttu-id="99fdc-105">(Обратите внимание, что `DebugView` доступен только в режиме отладки.)</span><span class="sxs-lookup"><span data-stu-id="99fdc-105">(Note that `DebugView` is available only in debug mode.)</span></span>  

![DebugView дерева выражения в отладчике Visual Studio](media/debugging-expression-trees-in-visual-studio/debugview_vb.png)

<span data-ttu-id="99fdc-107">Так как `DebugView` представляет собой строку, можно использовать [встроенный визуализатор текста](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) для его просмотра по нескольким строкам, выбрав **визуализатор текста** из меню со значком лупы рядом с меткой `DebugView`.</span><span class="sxs-lookup"><span data-stu-id="99fdc-107">Since `DebugView` is a string, you can use the [built-in Text Visualizer](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) to view it across multiple lines, by selecting **Text Visualizer** from the magnifying glass icon next to the `DebugView` label.</span></span>

 ![Визуализатор текста применяется к результатам DebugView](media/debugging-expression-trees-in-visual-studio/string_visualizer_vb.png)

<span data-ttu-id="99fdc-109">Кроме того, можно установить и использовать [пользовательский визуализатор](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) для деревьев выражений, таких как:</span><span class="sxs-lookup"><span data-stu-id="99fdc-109">Alternatively, you can install and use [a custom visualizer](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) for expression trees, such as:</span></span>

* <span data-ttu-id="99fdc-110">[Выражения для чтения](https://github.com/agileobjects/ReadableExpressions) ([лицензия MIT](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), доступная в [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)), отображают дерево выражения в виде кода C#:</span><span class="sxs-lookup"><span data-stu-id="99fdc-110">[Readable Expressions](https://github.com/agileobjects/ReadableExpressions) ([MIT license](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), available at the [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)), renders the expression tree as C# code:</span></span>

  ![Визуализатор выражений для чтения](media/debugging-expression-trees-in-visual-studio/readable_expressions_visualizer.png)

* <span data-ttu-id="99fdc-112">[Визуализатор дерева выражения](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) ([лицензии MIT](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)), который обеспечивает графическое представление дерева выражения, его свойства и связанные объекты; и может преобразовать дерево выражения, с помощью кода Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="99fdc-112">[Expression Tree Visualizer](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) ([MIT license](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)), provides a graphical view of the expression tree, its properties, and related objects; and can render the expression tree using Visual Basic code:</span></span>

  ![Визуализатор ExpressionToString](media/debugging-expression-trees-in-visual-studio/expression_to_string_visualizer_vb.png)

### <a name="to-open-a-visualizer-for-an-expression-tree"></a><span data-ttu-id="99fdc-114">Открытие визуализатора дерева выражения</span><span class="sxs-lookup"><span data-stu-id="99fdc-114">To open a visualizer for an expression tree</span></span>  
  
1. <span data-ttu-id="99fdc-115">Щелкните значок лупы рядом с деревом выражения в окне **Подсказки по данным**, **Контрольные значения**, **Видимые** или **Локальные**.</span><span class="sxs-lookup"><span data-stu-id="99fdc-115">Click the magnifying glass icon that appears next to the expression tree in **DataTips**, a **Watch** window, the **Autos** window, or the **Locals** window.</span></span>  
  
     <span data-ttu-id="99fdc-116">Отображается список доступных визуализаторов:</span><span class="sxs-lookup"><span data-stu-id="99fdc-116">A list of available visualizers is displayed.:</span></span> 

      ![Открытие визуализаторов из Visual Studio](media/debugging-expression-trees-in-visual-studio/expression_tree_visualizers_vb.png)

2. <span data-ttu-id="99fdc-118">Щелкните визуализатор, который необходимо использовать.</span><span class="sxs-lookup"><span data-stu-id="99fdc-118">Click the visualizer you want to use.</span></span>  

## <a name="see-also"></a><span data-ttu-id="99fdc-119">См. также</span><span class="sxs-lookup"><span data-stu-id="99fdc-119">See also</span></span>

- <span data-ttu-id="99fdc-120">[Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md) (Деревья выражений (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="99fdc-120">[Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)</span></span>
- [<span data-ttu-id="99fdc-121">Отладка в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="99fdc-121">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugging-in-visual-studio)
- [<span data-ttu-id="99fdc-122">Создание настраиваемых визуализаторов</span><span class="sxs-lookup"><span data-stu-id="99fdc-122">Create Custom Visualizers</span></span>](/visualstudio/debugger/create-custom-visualizers-of-data)
- [<span data-ttu-id="99fdc-123">`DebugView` Синтаксис</span><span class="sxs-lookup"><span data-stu-id="99fdc-123">`DebugView` syntax</span></span>](debugview-syntax.md)
