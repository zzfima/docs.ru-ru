---
title: Практическое руководство. Реализация интерфейса ITypedList
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ITypedList interface
- BindingList(Of T) class
- data binding [Windows Forms], implementing
- IBindingList interface
ms.assetid: 834cc15c-50bc-4a8b-a610-313d6a217357
ms.openlocfilehash: df4b009ca225b4bf4290398ccd7dd252c9189915
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57709820"
---
# <a name="how-to-implement-the-itypedlist-interface"></a><span data-ttu-id="63a7d-102">Практическое руководство. Реализация интерфейса ITypedList</span><span class="sxs-lookup"><span data-stu-id="63a7d-102">How to: Implement the ITypedList Interface</span></span>
<span data-ttu-id="63a7d-103">Реализуйте <xref:System.ComponentModel.ITypedList> интерфейс, чтобы включить обнаружение схемы для связываемого списка.</span><span class="sxs-lookup"><span data-stu-id="63a7d-103">Implement the <xref:System.ComponentModel.ITypedList> interface to enable discovery of the schema for a bindable list.</span></span>  
  
## <a name="example"></a><span data-ttu-id="63a7d-104">Пример</span><span class="sxs-lookup"><span data-stu-id="63a7d-104">Example</span></span>  
 <span data-ttu-id="63a7d-105">В следующем примере кода показано, как реализовать <xref:System.ComponentModel.ITypedList> интерфейс.</span><span class="sxs-lookup"><span data-stu-id="63a7d-105">The following code example demonstrates how to implement the <xref:System.ComponentModel.ITypedList> interface.</span></span> <span data-ttu-id="63a7d-106">Универсальный тип с именем `SortableBindingList` является производным от <xref:System.ComponentModel.BindingList%601> и реализующий <xref:System.ComponentModel.ITypedList> интерфейс.</span><span class="sxs-lookup"><span data-stu-id="63a7d-106">A generic type named `SortableBindingList` derives from the <xref:System.ComponentModel.BindingList%601> class and implements the <xref:System.ComponentModel.ITypedList> interface.</span></span> <span data-ttu-id="63a7d-107">Простой класс с именем `Customer` данных, который привязан к заголовку <xref:System.Windows.Forms.DataGridView> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="63a7d-107">A simple class named `Customer` provides data, which is bound to the header of a <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 [!code-csharp[System.ComponentModel.ITypedList#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.ITypedList/CS/SortableBindingList.cs#1)]
 [!code-vb[System.ComponentModel.ITypedList#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.ITypedList/VB/SortableBindingList.vb#1)]  
  
 [!code-csharp[System.ComponentModel.ITypedList#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.ITypedList/CS/Customer.cs#10)]
 [!code-vb[System.ComponentModel.ITypedList#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.ITypedList/VB/Customer.vb#10)]  
  
 [!code-csharp[System.ComponentModel.ITypedList#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.ITypedList/CS/Form1.cs#100)]
 [!code-vb[System.ComponentModel.ITypedList#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.ITypedList/VB/Form1.vb#100)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="63a7d-108">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="63a7d-108">Compiling the Code</span></span>  
 <span data-ttu-id="63a7d-109">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="63a7d-109">This example requires:</span></span>  
  
-   <span data-ttu-id="63a7d-110">ссылки на сборки System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="63a7d-110">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63a7d-111">См. также</span><span class="sxs-lookup"><span data-stu-id="63a7d-111">See also</span></span>
- <xref:System.ComponentModel.ITypedList>
- <xref:System.ComponentModel.BindingList%601>
- <xref:System.ComponentModel.IBindingList>
- [<span data-ttu-id="63a7d-112">Привязка данных и Windows Forms</span><span class="sxs-lookup"><span data-stu-id="63a7d-112">Data Binding and Windows Forms</span></span>](data-binding-and-windows-forms.md)
