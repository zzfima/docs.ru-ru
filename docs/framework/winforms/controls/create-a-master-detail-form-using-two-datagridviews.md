---
title: Создание формы "основной/подробности" с помощью двух элементов управления DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], master/detail form
- parent-child tables [Windows Forms], displaying on Windows Forms
- master-details lists [Windows Forms], creating
ms.assetid: 99f6e876-3f7f-4139-9063-e36587c95b02
ms.openlocfilehash: d317f4e592790c9b48b539b1601814569e14529f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76737332"
---
# <a name="how-to-create-a-masterdetail-form-using-two-windows-forms-datagridview-controls"></a><span data-ttu-id="70342-102">Практическое руководство. Отображение главного и подчиненного представлений данных с использованием двух элементов управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="70342-102">How to: Create a Master/Detail Form Using Two Windows Forms DataGridView Controls</span></span>
<span data-ttu-id="70342-103">В приведенном ниже примере кода создаются главная и подчиненная формы с использованием двух элементов управления <xref:System.Windows.Forms.DataGridView>, привязанных к двум компонентам <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="70342-103">The following code example creates a master/detail form using two <xref:System.Windows.Forms.DataGridView> controls bound to two <xref:System.Windows.Forms.BindingSource> components.</span></span> <span data-ttu-id="70342-104">Источником данных является объект <xref:System.Data.DataSet>, содержащий таблицы `Customers` и `Orders` из образца базы данных SQL Server Northwind и объект <xref:System.Data.DataRelation>, связывающий таблицы через столбец `CustomerID`.</span><span class="sxs-lookup"><span data-stu-id="70342-104">The data source is a <xref:System.Data.DataSet> that contains the `Customers` and `Orders` tables from the Northwind SQL Server sample database along with a <xref:System.Data.DataRelation> that relates the two through the `CustomerID` column.</span></span>  
  
 <span data-ttu-id="70342-105">Один источник <xref:System.Windows.Forms.BindingSource> привязан к родительской таблице `Customers` в наборе данных.</span><span class="sxs-lookup"><span data-stu-id="70342-105">One <xref:System.Windows.Forms.BindingSource> is bound to the parent `Customers` table in the data set.</span></span> <span data-ttu-id="70342-106">Эти данные отображаются в главном элементе управления <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="70342-106">This data is displayed in the master <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="70342-107">Другой источник <xref:System.Windows.Forms.BindingSource> привязан к первому соединителю данных.</span><span class="sxs-lookup"><span data-stu-id="70342-107">The other <xref:System.Windows.Forms.BindingSource> is bound to the first data connector.</span></span> <span data-ttu-id="70342-108">Свойству <xref:System.Windows.Forms.BindingSource.DataMember%2A> второго источника <xref:System.Windows.Forms.BindingSource> присвоено имя <xref:System.Data.DataRelation>.</span><span class="sxs-lookup"><span data-stu-id="70342-108">The <xref:System.Windows.Forms.BindingSource.DataMember%2A> property of the second <xref:System.Windows.Forms.BindingSource> is set to the <xref:System.Data.DataRelation> name.</span></span> <span data-ttu-id="70342-109">Это заставляет связанный подчиненный элемент управления <xref:System.Windows.Forms.DataGridView> отображать строки дочерней таблицы `Orders`, соответствующие текущей строке главного элемента управления <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="70342-109">This causes the associated detail <xref:System.Windows.Forms.DataGridView> control to display the rows of the child `Orders` table that correspond to the current row in the master <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <span data-ttu-id="70342-110">Полное описание этого примера кода см. в разделе [Пошаговое руководство. Создание формы "основной/подробности" с помощью двух элементов управления Windows Forms DataGridView](creating-a-master-detail-form-using-two-datagridviews.md).</span><span class="sxs-lookup"><span data-stu-id="70342-110">For a complete explanation of this code example, see [Walkthrough: Creating a Master/Detail Form Using Two Windows Forms DataGridView Controls](creating-a-master-detail-form-using-two-datagridviews.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="70342-111">Пример</span><span class="sxs-lookup"><span data-stu-id="70342-111">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="70342-112">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="70342-112">Compiling the Code</span></span>  
 <span data-ttu-id="70342-113">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="70342-113">This example requires:</span></span>  
  
 <span data-ttu-id="70342-114">ссылки на сборки System, System.Data, System.Windows.Forms и System.XML.</span><span class="sxs-lookup"><span data-stu-id="70342-114">References to the System, System.Data, System.Windows.Forms, and System.XML assemblies.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="70342-115">Безопасность .NET Framework</span><span class="sxs-lookup"><span data-stu-id="70342-115">.NET Framework Security</span></span>  
 <span data-ttu-id="70342-116">Хранение конфиденциальных сведений (например, пароля) в строке подключения может повлиять на безопасность приложения.</span><span class="sxs-lookup"><span data-stu-id="70342-116">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="70342-117">Использование проверки подлинности Windows (также называемой встроенными средствами безопасности) — более безопасный способ управления доступом к базе данных.</span><span class="sxs-lookup"><span data-stu-id="70342-117">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="70342-118">Дополнительные сведения см. в разделе [Защита сведений о подключении](../../data/adonet/protecting-connection-information.md).</span><span class="sxs-lookup"><span data-stu-id="70342-118">For more information, see [Protecting Connection Information](../../data/adonet/protecting-connection-information.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70342-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="70342-119">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="70342-120">Пример. Создание главного и подчиненного представлений данных с использованием двух элементов управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="70342-120">Walkthrough: Creating a Master/Detail Form Using Two Windows Forms DataGridView Controls</span></span>](creating-a-master-detail-form-using-two-datagridviews.md)
- [<span data-ttu-id="70342-121">Отображение данных с помощью элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="70342-121">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="70342-122">Защита сведений о подключении</span><span class="sxs-lookup"><span data-stu-id="70342-122">Protecting Connection Information</span></span>](../../data/adonet/protecting-connection-information.md)
