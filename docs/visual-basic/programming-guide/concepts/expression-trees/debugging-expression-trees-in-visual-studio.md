---
title: Отладка деревьев выражений в Visual Studio
ms.date: 07/20/2015
ms.assetid: 492cc28f-b7a2-4c47-b582-b3c437b8a5d5
ms.openlocfilehash: c6c44d079ab0854b2325b82d3569280752da32fb
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266837"
---
# <a name="debugging-expression-trees-in-visual-studio-visual-basic"></a><span data-ttu-id="cedc3-102">Отладка деревьев выражения в визуальной студии (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cedc3-102">Debugging Expression Trees in Visual Studio (Visual Basic)</span></span>
<span data-ttu-id="cedc3-103">При отладке приложений можно анализировать структуру и содержимое деревьев выражений.</span><span class="sxs-lookup"><span data-stu-id="cedc3-103">You can analyze the structure and content of expression trees when you debug your applications.</span></span> <span data-ttu-id="cedc3-104">Чтобы получить краткий обзор структуры дерева выражения, вы можете использовать свойство `DebugView`, которое представляет деревья выражений, [используя специальный синтаксис](debugview-syntax.md).</span><span class="sxs-lookup"><span data-stu-id="cedc3-104">To get a quick overview of the expression tree structure, you can use the `DebugView` property, which represents expression trees [using a special syntax](debugview-syntax.md).</span></span> <span data-ttu-id="cedc3-105">(Обратите внимание, что `DebugView` доступен только в режиме отладки.)</span><span class="sxs-lookup"><span data-stu-id="cedc3-105">(Note that `DebugView` is available only in debug mode.)</span></span>  

![Скриншот дерева выражения DebugView.](media/debugging-expression-trees-in-visual-studio/debugview-visual-basic.png)

<span data-ttu-id="cedc3-107">Так как `DebugView` представляет собой строку, можно использовать [встроенный визуализатор текста](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) для его просмотра по нескольким строкам, выбрав **визуализатор текста** из меню со значком лупы рядом с меткой `DebugView`.</span><span class="sxs-lookup"><span data-stu-id="cedc3-107">Since `DebugView` is a string, you can use the [built-in Text Visualizer](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) to view it across multiple lines, by selecting **Text Visualizer** from the magnifying glass icon next to the `DebugView` label.</span></span>

 ![Скриншот text Visualizer применяется к результатам DebugView.](media/debugging-expression-trees-in-visual-studio/string-visualizer-vb.png)

<span data-ttu-id="cedc3-109">Или вы можете установить и использовать [пользовательский визуализатор](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) для деревьев выражений, например:</span><span class="sxs-lookup"><span data-stu-id="cedc3-109">Alternatively, you can install and use [a custom visualizer](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) for expression trees, such as:</span></span>

- <span data-ttu-id="cedc3-110">[Выражения для чтения](https://github.com/agileobjects/ReadableExpressions) ([лицензия MIT](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), доступная в [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)), отображают дерево выражения в виде кода C#:</span><span class="sxs-lookup"><span data-stu-id="cedc3-110">[Readable Expressions](https://github.com/agileobjects/ReadableExpressions) ([MIT license](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), available at the [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)), renders the expression tree as C# code:</span></span>

  ![Снимок экрана: визуализатор доступных для чтения выражений](media/debugging-expression-trees-in-visual-studio/readable-expressions-visualizer.png)

- <span data-ttu-id="cedc3-112">[Expression Tree Visualizer](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) [(лицензия MIT),](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)обеспечивает графическое представление дерева выражения, его свойств и связанных с ними объектов; и может визуализировать дерево выражения с помощью визуального базового кода:</span><span class="sxs-lookup"><span data-stu-id="cedc3-112">[Expression Tree Visualizer](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) ([MIT license](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)), provides a graphical view of the expression tree, its properties, and related objects; and can render the expression tree using Visual Basic code:</span></span>

  ![Скриншот визуализатора ExpressionToString.](media/debugging-expression-trees-in-visual-studio/expression-to-string-visualizer-vb.png)

### <a name="to-open-a-visualizer-for-an-expression-tree"></a><span data-ttu-id="cedc3-114">Открытие визуализатора дерева выражения</span><span class="sxs-lookup"><span data-stu-id="cedc3-114">To open a visualizer for an expression tree</span></span>  
  
1. <span data-ttu-id="cedc3-115">Щелкните значок лупы рядом с деревом выражения в окне **Подсказки по данным**, **Контрольные значения**, **Видимые** или **Локальные**.</span><span class="sxs-lookup"><span data-stu-id="cedc3-115">Click the magnifying glass icon that appears next to the expression tree in **DataTips**, a **Watch** window, the **Autos** window, or the **Locals** window.</span></span>  
  
    <span data-ttu-id="cedc3-116">Отображается список доступных визуализаторов:</span><span class="sxs-lookup"><span data-stu-id="cedc3-116">A list of available visualizers is displayed.:</span></span>

    ![Скриншот открывающихся визуализаторов пользователя от Visual Studio.](media/debugging-expression-trees-in-visual-studio/expression-tree-visualizers-vb.png)

2. <span data-ttu-id="cedc3-118">Щелкните визуализатор, который необходимо использовать.</span><span class="sxs-lookup"><span data-stu-id="cedc3-118">Click the visualizer you want to use.</span></span>  

## <a name="see-also"></a><span data-ttu-id="cedc3-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="cedc3-119">See also</span></span>

- <span data-ttu-id="cedc3-120">[Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md) (Деревья выражений (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="cedc3-120">[Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)</span></span>
- [<span data-ttu-id="cedc3-121">Отладка в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="cedc3-121">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugger-feature-tour)
- [<span data-ttu-id="cedc3-122">Создание настраиваемых визуализаторов</span><span class="sxs-lookup"><span data-stu-id="cedc3-122">Create Custom Visualizers</span></span>](/visualstudio/debugger/create-custom-visualizers-of-data)
- [<span data-ttu-id="cedc3-123">Синтаксис `DebugView`</span><span class="sxs-lookup"><span data-stu-id="cedc3-123">`DebugView` syntax</span></span>](debugview-syntax.md)
