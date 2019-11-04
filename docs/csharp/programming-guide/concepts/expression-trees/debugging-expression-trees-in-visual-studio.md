---
title: Отладка деревьев выражений в Visual Studio (C#)
ms.date: 07/20/2015
ms.assetid: 1369fa25-0fbd-4b92-98d0-8df79c49c27a
ms.openlocfilehash: 30f538712881e41b4fd0e62d06f74373d755ea40
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2019
ms.locfileid: "73195680"
---
# <a name="debugging-expression-trees-in-visual-studio-c"></a><span data-ttu-id="e2370-102">Отладка деревьев выражений в Visual Studio (C#)</span><span class="sxs-lookup"><span data-stu-id="e2370-102">Debugging Expression Trees in Visual Studio (C#)</span></span>
<span data-ttu-id="e2370-103">При отладке приложений можно анализировать структуру и содержимое деревьев выражений.</span><span class="sxs-lookup"><span data-stu-id="e2370-103">You can analyze the structure and content of expression trees when you debug your applications.</span></span> <span data-ttu-id="e2370-104">Чтобы получить краткий обзор структуры дерева выражения, вы можете использовать свойство `DebugView`, которое представляет деревья выражений, [используя специальный синтаксис](debugview-syntax.md).</span><span class="sxs-lookup"><span data-stu-id="e2370-104">To get a quick overview of the expression tree structure, you can use the `DebugView` property, which represents expression trees [using a special syntax](debugview-syntax.md).</span></span> <span data-ttu-id="e2370-105">(Обратите внимание, что `DebugView` доступен только в режиме отладки.)</span><span class="sxs-lookup"><span data-stu-id="e2370-105">(Note that `DebugView` is available only in debug mode.)</span></span>  

![Снимок экрана: DebugView дерева выражений в отладчике VS](media/debugging-expression-trees-in-visual-studio/debugview-expression-tree.png)

<span data-ttu-id="e2370-107">Так как `DebugView` представляет собой строку, можно использовать [встроенный визуализатор текста](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) для его просмотра по нескольким строкам, выбрав **визуализатор текста** из меню со значком лупы рядом с меткой `DebugView`.</span><span class="sxs-lookup"><span data-stu-id="e2370-107">Since `DebugView` is a string, you can use the [built-in Text Visualizer](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) to view it across multiple lines, by selecting **Text Visualizer** from the magnifying glass icon next to the `DebugView` label.</span></span>

 ![Снимок экрана: визуализатор текста, примененный к результатам DebugView](media/debugging-expression-trees-in-visual-studio/string-visualizer-debugview.png)

<span data-ttu-id="e2370-109">Или вы можете установить и использовать [пользовательский визуализатор](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) для деревьев выражений, например:</span><span class="sxs-lookup"><span data-stu-id="e2370-109">Alternatively, you can install and use [a custom visualizer](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) for expression trees, such as:</span></span>

- <span data-ttu-id="e2370-110">[Выражения для чтения](https://github.com/agileobjects/ReadableExpressions) ([лицензия MIT](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), доступная в [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)), отображают дерево выражения в виде кода C#:</span><span class="sxs-lookup"><span data-stu-id="e2370-110">[Readable Expressions](https://github.com/agileobjects/ReadableExpressions) ([MIT license](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), available at the [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)), renders the expression tree as C# code:</span></span>

  ![Снимок экрана: визуализатор доступных для чтения выражений](media/debugging-expression-trees-in-visual-studio/readable-expressions-visualizer.png)

- <span data-ttu-id="e2370-112">[Визуализатор дерева выражения](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) ([лицензия MIT](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)) предоставляет графическое представление дерева выражения, его свойства и связанные объекты:</span><span class="sxs-lookup"><span data-stu-id="e2370-112">[Expression Tree Visualizer](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) ([MIT license](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)), provides a graphical view of the expression tree, its properties, and related objects:</span></span>

  ![Снимок экрана: визуализатор дерева выражений](media/debugging-expression-trees-in-visual-studio/expression-to-string-visualizer.png)

### <a name="to-open-a-visualizer-for-an-expression-tree"></a><span data-ttu-id="e2370-114">Открытие визуализатора дерева выражения</span><span class="sxs-lookup"><span data-stu-id="e2370-114">To open a visualizer for an expression tree</span></span>  
  
1. <span data-ttu-id="e2370-115">Щелкните значок лупы рядом с деревом выражения в окне **Подсказки по данным**, **Контрольные значения**, **Видимые** или **Локальные**.</span><span class="sxs-lookup"><span data-stu-id="e2370-115">Click the magnifying glass icon that appears next to the expression tree in **DataTips**, a **Watch** window, the **Autos** window, or the **Locals** window.</span></span>  

    <span data-ttu-id="e2370-116">Отображается список доступных визуализаторов:</span><span class="sxs-lookup"><span data-stu-id="e2370-116">A list of available visualizers is displayed.:</span></span> 

    ![Снимок экрана: открытие визуализаторов из Visual Studio](media/debugging-expression-trees-in-visual-studio/expression-tree-visualizers.png)

2. <span data-ttu-id="e2370-118">Щелкните визуализатор, который необходимо использовать.</span><span class="sxs-lookup"><span data-stu-id="e2370-118">Click the visualizer you want to use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2370-119">См. также</span><span class="sxs-lookup"><span data-stu-id="e2370-119">See also</span></span>

- <span data-ttu-id="e2370-120">[Expression Trees (C#)](./index.md) (Деревья выражений (C#))</span><span class="sxs-lookup"><span data-stu-id="e2370-120">[Expression Trees (C#)](./index.md)</span></span>
- [<span data-ttu-id="e2370-121">Отладка в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e2370-121">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugger-feature-tour)
- [<span data-ttu-id="e2370-122">Создание настраиваемых визуализаторов</span><span class="sxs-lookup"><span data-stu-id="e2370-122">Create Custom Visualizers</span></span>](/visualstudio/debugger/create-custom-visualizers-of-data)
- [<span data-ttu-id="e2370-123">Синтаксис `DebugView`</span><span class="sxs-lookup"><span data-stu-id="e2370-123">`DebugView` syntax</span></span>](debugview-syntax.md)
