---
title: "Практическое руководство. Выбор членов для проверки на конфликты параллельности"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: d2cda293-1e2f-4878-af0e-5aaf0d092120
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 6c13c5d6578f27155b87744ed8730f5fae2e1e25
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-which-members-are-tested-for-concurrency-conflicts"></a><span data-ttu-id="89032-102">Практическое руководство. Выбор членов для проверки на конфликты параллельности</span><span class="sxs-lookup"><span data-stu-id="89032-102">How to: Specify Which Members are Tested for Concurrency Conflicts</span></span>
<span data-ttu-id="89032-103">Применить один из трех перечислений к [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> свойство <xref:System.Data.Linq.Mapping.ColumnAttribute> проверяет атрибут, чтобы указать, какие члены должны быть включены в обновления для обнаружения конфликтов оптимистичного параллелизма.</span><span class="sxs-lookup"><span data-stu-id="89032-103">Apply one of three enums to the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property on a <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to specify which members are to be included in update checks for the detection of optimistic concurrency conflicts.</span></span>  
  
 <span data-ttu-id="89032-104">Свойство <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> (сопоставляемое во время разработки) используется в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] вместе с функциями параллелизма времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="89032-104">The <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property (mapped at design time) is used together with run-time concurrency features in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="89032-105">Дополнительные сведения см. в разделе [оптимистичного параллелизма: Обзор](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span><span class="sxs-lookup"><span data-stu-id="89032-105">For more information, see [Optimistic Concurrency: Overview](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="89032-106">Если ни одному члену не присвоено значение `IsVersion=true`, исходные значения членов сравниваются с текущим состоянием базы данных.</span><span class="sxs-lookup"><span data-stu-id="89032-106">Original member values are compared with the current database state as long as no member is designated as `IsVersion=true`.</span></span> <span data-ttu-id="89032-107">Для получения дополнительной информации см. <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span><span class="sxs-lookup"><span data-stu-id="89032-107">For more information, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span></span>  
  
 <span data-ttu-id="89032-108">Примеры кода см. в разделе <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span><span class="sxs-lookup"><span data-stu-id="89032-108">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span></span>  
  
### <a name="to-always-use-this-member-for-detecting-conflicts"></a><span data-ttu-id="89032-109">Чтобы всегда использовать этот член для обнаружения конфликтов, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="89032-109">To always use this member for detecting conflicts</span></span>  
  
1.  <span data-ttu-id="89032-110">Добавьте свойство <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> атрибуту <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="89032-110">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2.  <span data-ttu-id="89032-111">Задайте свойству <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> значение `Always`.</span><span class="sxs-lookup"><span data-stu-id="89032-111">Set the <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property value to `Always`.</span></span>  
  
### <a name="to-never-use-this-member-for-detecting-conflicts"></a><span data-ttu-id="89032-112">Чтобы никогда не использовать этот член для обнаружения конфликтов, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="89032-112">To never use this member for detecting conflicts</span></span>  
  
1.  <span data-ttu-id="89032-113">Добавьте свойство <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> атрибуту <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="89032-113">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2.  <span data-ttu-id="89032-114">Задайте свойству <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> значение `Never`.</span><span class="sxs-lookup"><span data-stu-id="89032-114">Set the <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property value to `Never`.</span></span>  
  
### <a name="to-use-this-member-for-detecting-conflicts-only-when-the-application-has-changed-the-value-of-the-member"></a><span data-ttu-id="89032-115">Чтобы использовать этот член для обнаружения конфликтов, только когда приложение изменяет его значение, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="89032-115">To use this member for detecting conflicts only when the application has changed the value of the member</span></span>  
  
1.  <span data-ttu-id="89032-116">Добавьте свойство <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> атрибуту <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="89032-116">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2.  <span data-ttu-id="89032-117">Задайте свойству <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> значение `WhenChanged`.</span><span class="sxs-lookup"><span data-stu-id="89032-117">Set the <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property value to `WhenChanged`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="89032-118">Пример</span><span class="sxs-lookup"><span data-stu-id="89032-118">Example</span></span>  
 <span data-ttu-id="89032-119">В следующем примере указывается, что объекты `HomePage` никогда не должны включаться в проверки обновлений.</span><span class="sxs-lookup"><span data-stu-id="89032-119">The following example specifies that `HomePage` objects should never be tested during update checks.</span></span> <span data-ttu-id="89032-120">Для получения дополнительной информации см. <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span><span class="sxs-lookup"><span data-stu-id="89032-120">For more information, see <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span></span>  
  
 [!code-csharp[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.mapping.updatecheck/cs/northwind.cs#1)]
 [!code-vb[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.mapping.updatecheck/vb/northwind.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="89032-121">См. также</span><span class="sxs-lookup"><span data-stu-id="89032-121">See Also</span></span>  
 [<span data-ttu-id="89032-122">Как: управление конфликтами изменений</span><span class="sxs-lookup"><span data-stu-id="89032-122">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)  
 [<span data-ttu-id="89032-123">Внесение и отправка изменений данных</span><span class="sxs-lookup"><span data-stu-id="89032-123">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
