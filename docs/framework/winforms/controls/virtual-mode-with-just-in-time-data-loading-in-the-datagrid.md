---
title: Реализация виртуального режима с JIT-загрузкой данных в элементе управления DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], just-in-time data loading
- data [Windows Forms], managing large data sets
- DataGridView control [Windows Forms], virtual mode
- just-in-time data loading
- DataGridView control [Windows Forms], large data sets
- virtual mode [Windows Forms], just-in-time data loading
ms.assetid: 33825f92-7a22-40ee-86d9-9a2ed1ead7b7
ms.openlocfilehash: bbe98d3c317a7625b36b729f0be23ea20f65dec0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745435"
---
# <a name="how-to-implement-virtual-mode-with-just-in-time-data-loading-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="5fffa-102">Практическое руководство. Реализация виртуального режима с JIT-загрузкой данных для элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5fffa-102">How to: Implement Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="5fffa-103">В примере кода ниже показано, как использовать виртуальный режим в элементе управления <xref:System.Windows.Forms.DataGridView> с кэшем данных, который подгружает данные с сервера только в случае необходимости.</span><span class="sxs-lookup"><span data-stu-id="5fffa-103">The following code example shows how to use virtual mode in the <xref:System.Windows.Forms.DataGridView> control with a data cache that loads data from a server only when it is needed.</span></span> <span data-ttu-id="5fffa-104">Этот пример подробно описан в статье [Реализация виртуального режима с JIT-загрузкой данных в элементе управления Windows Forms DataGridView](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md).</span><span class="sxs-lookup"><span data-stu-id="5fffa-104">This example is described in detail in [Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5fffa-105">Пример</span><span class="sxs-lookup"><span data-stu-id="5fffa-105">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#000](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#000)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5fffa-106">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="5fffa-106">Compiling the Code</span></span>  
 <span data-ttu-id="5fffa-107">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="5fffa-107">This example requires:</span></span>  
  
- <span data-ttu-id="5fffa-108">ссылки на сборки System, System.Data, System.Windows.Forms и System.XML;</span><span class="sxs-lookup"><span data-stu-id="5fffa-108">References to the System, System.Data, System.Xml, and System.Windows.Forms assemblies.</span></span>  
  
- <span data-ttu-id="5fffa-109">доступ к серверу SQL Server с установленным образцом базы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="5fffa-109">Access to a server with the Northwind SQL Server sample database installed.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="5fffa-110">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="5fffa-110">.NET Framework Security</span></span>  
 <span data-ttu-id="5fffa-111">Хранение конфиденциальных сведений (например, пароля) в строке подключения может повлиять на безопасность приложения.</span><span class="sxs-lookup"><span data-stu-id="5fffa-111">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="5fffa-112">Использование проверки подлинности Windows (также называемой встроенными средствами безопасности) — более безопасный способ управления доступом к базе данных.</span><span class="sxs-lookup"><span data-stu-id="5fffa-112">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="5fffa-113">Дополнительные сведения см. в разделе [Защита сведений о подключении](../../data/adonet/protecting-connection-information.md).</span><span class="sxs-lookup"><span data-stu-id="5fffa-113">For more information, see [Protecting Connection Information](../../data/adonet/protecting-connection-information.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fffa-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="5fffa-114">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>
- <xref:System.Windows.Forms.DataGridView.CellValueNeeded>
- [<span data-ttu-id="5fffa-115">Реализация виртуального режима с JIT-загрузкой данных для элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5fffa-115">Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control</span></span>](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)
- [<span data-ttu-id="5fffa-116">Оптимизация производительности элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5fffa-116">Performance Tuning in the Windows Forms DataGridView Control</span></span>](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="5fffa-117">Виртуальный режим элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5fffa-117">Virtual Mode in the Windows Forms DataGridView Control</span></span>](virtual-mode-in-the-windows-forms-datagridview-control.md)
