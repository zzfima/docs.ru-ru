---
title: Привязка элемента управления к объекту фабрики
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], binding
- factory objects [Windows Forms], binding to
- BindingSource component [Windows Forms], binding to a factory object
- BindingSource component [Windows Forms], examples
ms.assetid: 7d59af89-ff82-41d8-a48a-f1fbae788b0d
ms.openlocfilehash: 2b4d9aca3345a0cb1e7e995f66a8982dee983ca8
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745090"
---
# <a name="how-to-bind-a-windows-forms-control-to-a-factory-object"></a><span data-ttu-id="9a2d6-102">Практическое руководство. Связывание элемента управления с объектом-фабрикой в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9a2d6-102">How to: Bind a Windows Forms Control to a Factory Object</span></span>
<span data-ttu-id="9a2d6-103">При создании элементов управления, взаимодействующих с данными, иногда требуется привязать элемент управления к объекту или методу, создающему другие объекты.</span><span class="sxs-lookup"><span data-stu-id="9a2d6-103">When you are building controls that interact with data, you will sometimes find it necessary to bind a control to an object or method that generates other objects.</span></span> <span data-ttu-id="9a2d6-104">Такой объект или метод называется фабрикой.</span><span class="sxs-lookup"><span data-stu-id="9a2d6-104">Such an object or method is called a factory.</span></span> <span data-ttu-id="9a2d6-105">Источник данных может быть, например, возвращаемым значением вызова метода, а не объектом в памяти или типом.</span><span class="sxs-lookup"><span data-stu-id="9a2d6-105">Your data source might be, for example, the return value from a method call, instead of an object in memory or a type.</span></span> <span data-ttu-id="9a2d6-106">Можно привязать элемент управления к такому типу источника данных при условии, что источник возвращает коллекцию.</span><span class="sxs-lookup"><span data-stu-id="9a2d6-106">You can bind a control to this kind of data source as long as the source returns a collection.</span></span>  
  
 <span data-ttu-id="9a2d6-107">Элемент управления можно легко привязать к объекту фабрики с помощью элемента управления <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="9a2d6-107">You can easily bind a control to a factory object by using the <xref:System.Windows.Forms.BindingSource> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9a2d6-108">Пример</span><span class="sxs-lookup"><span data-stu-id="9a2d6-108">Example</span></span>  
 <span data-ttu-id="9a2d6-109">В примере ниже показано, как связать элемент управления <xref:System.Windows.Forms.DataGridView> с методом фабрики с помощью элемента управления <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="9a2d6-109">The following example demonstrates how to bind a <xref:System.Windows.Forms.DataGridView> control to a factory method by using a <xref:System.Windows.Forms.BindingSource> control.</span></span> <span data-ttu-id="9a2d6-110">Метод фабрики называется `GetOrdersByCustomerId` и возвращает все заказы для данного клиента в базе данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="9a2d6-110">The factory method is named `GetOrdersByCustomerId`, and it returns all the orders for a given customer in the Northwind database.</span></span>  
  
 [!code-cpp[System.Windows.Forms.DataConnector.BindToFactory#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindToFactory/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnector.BindToFactory#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindToFactory/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.BindToFactory#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindToFactory/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9a2d6-111">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="9a2d6-111">Compiling the Code</span></span>  
 <span data-ttu-id="9a2d6-112">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="9a2d6-112">This example requires:</span></span>  
  
- <span data-ttu-id="9a2d6-113">ссылки на сборки System, System.Data, System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="9a2d6-113">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a2d6-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="9a2d6-114">See also</span></span>

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="9a2d6-115">Компонент BindingSource</span><span class="sxs-lookup"><span data-stu-id="9a2d6-115">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="9a2d6-116">Практическое руководство. Связывание элемента управления с типом в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9a2d6-116">How to: Bind a Windows Forms Control to a Type</span></span>](how-to-bind-a-windows-forms-control-to-a-type.md)
