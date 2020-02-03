---
title: Привязка элемента управления к типу
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], binding to a type
- BindingSource component [Windows Forms], binding to a type
- types [Windows Forms], binding controls to
ms.assetid: 94faeebb-d2bc-45d6-86d7-96a42661b43d
ms.openlocfilehash: 0bc1f92ee8922990bd0e461655168f5618ba39a6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744989"
---
# <a name="how-to-bind-a-windows-forms-control-to-a-type"></a><span data-ttu-id="173a2-102">Практическое руководство. Связывание элемента управления с типом в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="173a2-102">How to: Bind a Windows Forms Control to a Type</span></span>
<span data-ttu-id="173a2-103">При создании элементов управления, взаимодействующих с данными, иногда бывает нужно привязать элемент управления к типу, а не к объекту.</span><span class="sxs-lookup"><span data-stu-id="173a2-103">When you are building controls that interact with data, you will sometimes find it necessary to bind a control to a type, rather than an object.</span></span> <span data-ttu-id="173a2-104">Такая ситуация особенно часто возникает на этапе разработки, когда данные недоступны, но все равно нужно, чтобы элемент управления отображал данные из открытого интерфейса типа.</span><span class="sxs-lookup"><span data-stu-id="173a2-104">This situation arises especially at design time, when data may not be available, but your data-bound controls still need to display information from a type's public interface.</span></span> <span data-ttu-id="173a2-105">Например, вы привязываете элемент управления <xref:System.Windows.Forms.DataGridView> к объекту, предоставляемому веб-службой, и хотите, чтобы во время разработки элемент управления <xref:System.Windows.Forms.DataGridView> помечал свои столбцы именами членов пользовательского типа.</span><span class="sxs-lookup"><span data-stu-id="173a2-105">For example, you may bind a <xref:System.Windows.Forms.DataGridView> control to an object exposed by a Web service and want the <xref:System.Windows.Forms.DataGridView> control to label its columns at design time with the member names of a custom type.</span></span>  
  
 <span data-ttu-id="173a2-106">Элемент управления можно легко привязать к типу с помощью компонента <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="173a2-106">You can easily bind a control to a type with the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
## <a name="example"></a><span data-ttu-id="173a2-107">Пример</span><span class="sxs-lookup"><span data-stu-id="173a2-107">Example</span></span>  
 <span data-ttu-id="173a2-108">В примере кода ниже показано, как привязать элемент управления <xref:System.Windows.Forms.DataGridView> к пользовательскому типу с помощью компонента <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="173a2-108">The following code example demonstrates how to bind a <xref:System.Windows.Forms.DataGridView> control to a custom type by using a <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="173a2-109">После запуска примера можно увидеть, что <xref:System.Windows.Forms.DataGridView> пометил столбцы, отражающие свойства объекта `Customer`, перед заполнением элемента управления данными.</span><span class="sxs-lookup"><span data-stu-id="173a2-109">When you run the example, you'll notice the <xref:System.Windows.Forms.DataGridView> has labeled columns that reflect the properties of a `Customer` object, before the control is populated with data.</span></span> <span data-ttu-id="173a2-110">В примере есть кнопка Add Customer (Добавить клиента) для добавления данных в элемент управления <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="173a2-110">The example has an Add Customer button to add data to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="173a2-111">При нажатии на кнопку новый объект `Customer` добавляется в <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="173a2-111">When you click the button, a new `Customer` object is added to the <xref:System.Windows.Forms.BindingSource>.</span></span> <span data-ttu-id="173a2-112">В реальном сценарии данные можно было бы получить путем вызова веб-службы или другого источника данных.</span><span class="sxs-lookup"><span data-stu-id="173a2-112">In a real-world scenario, the data might be obtained by a call to a Web service or other data source.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataConnector.BindingToType#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindingToType/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.BindingToType#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindingToType/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="173a2-113">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="173a2-113">Compiling the Code</span></span>  
 <span data-ttu-id="173a2-114">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="173a2-114">This example requires:</span></span>  
  
- <span data-ttu-id="173a2-115">ссылки на сборки System и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="173a2-115">References to the System and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="173a2-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="173a2-116">See also</span></span>

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="173a2-117">Компонент BindingSource</span><span class="sxs-lookup"><span data-stu-id="173a2-117">BindingSource Component</span></span>](bindingsource-component.md)
