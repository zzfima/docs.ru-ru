---
title: "Выполнение в массивах строковых операций, не зависящих от языка и региональных параметров"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- culture-insensitive string operations, in arrays
- arrays [.NET Framework], culture-insensitive string operations
- comparer parameter
ms.assetid: f12922e1-6234-4165-8896-63f0653ab478
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: d273fbaa792092f5ea56bfa59392794b6728ed67
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="performing-culture-insensitive-string-operations-in-arrays"></a><span data-ttu-id="4bacb-102">Выполнение в массивах строковых операций, не зависящих от языка и региональных параметров</span><span class="sxs-lookup"><span data-stu-id="4bacb-102">Performing Culture-Insensitive String Operations in Arrays</span></span>
<span data-ttu-id="4bacb-103">Перегруженные версии методов <xref:System.Array.Sort%2A?displayProperty=nameWithType> и <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType> выполняют сортировку с учетом языка и региональных параметров, используя свойство <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4bacb-103">Overloads of the <xref:System.Array.Sort%2A?displayProperty=nameWithType> and <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType> methods perform culture-sensitive sorts by default using the <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="4bacb-104">Результат, возвращаемый этими методами, зависит от порядка сортировки в параметрах языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="4bacb-104">Culture-sensitive results returned by these methods can vary by culture due to differences in sort orders.</span></span> <span data-ttu-id="4bacb-105">Чтобы результат не зависел от языка и региональных параметров, используйте перегрузки этого метода, которые принимают параметр `comparer`.</span><span class="sxs-lookup"><span data-stu-id="4bacb-105">To eliminate culture-sensitive behavior, use one of the overloads of this method that accepts a `comparer` parameter.</span></span> <span data-ttu-id="4bacb-106">Параметр `comparer` указывает реализацию <xref:System.Collections.IComparer>, которую нужно использовать при сравнении элементов массива.</span><span class="sxs-lookup"><span data-stu-id="4bacb-106">The `comparer` parameter specifies the <xref:System.Collections.IComparer> implementation to use when comparing elements in the array.</span></span> <span data-ttu-id="4bacb-107">Укажите в этом параметре пользовательский инвариантный класс сравнения, который использует <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4bacb-107">For the parameter, specify a custom invariant comparer class that uses <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="4bacb-108">Пример настраиваемого инвариантного класса сравнения предлагается в подразделе "Использование класса SortedList" статьи [Выполнение в коллекциях строковых операций, не зависящих от языка и региональных параметров](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="4bacb-108">An example of a custom invariant comparer class is provided in the "Using the SortedList Class" subtopic of the [Performing Culture-Insensitive String Operations in Collections](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-collections.md) topic.</span></span>  
  
 <span data-ttu-id="4bacb-109">**Примечание**. Если передать в метод сравнения **CultureInfo.InvariantCulture**, сравнение выполняется без учета языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="4bacb-109">**Note** Passing **CultureInfo.InvariantCulture** to a comparison method does perform a culture-insensitive comparison.</span></span> <span data-ttu-id="4bacb-110">Однако при этом не выполняется нелингвистическое сравнение, например для путей к файлам, разделов реестра и переменных среды.</span><span class="sxs-lookup"><span data-stu-id="4bacb-110">However, it does not cause a non-linguistic comparison, for example, for file paths, registry keys, and environment variables.</span></span> <span data-ttu-id="4bacb-111">Также не поддерживается принятие решений по безопасности на основе результата сравнения.</span><span class="sxs-lookup"><span data-stu-id="4bacb-111">Neither does it support security decisions based on the comparison result.</span></span> <span data-ttu-id="4bacb-112">Для нелингвистического сравнения и (или) поддержки принятия решений по безопасности в приложении следует использовать метод сравнения, который принимает значение <xref:System.StringComparison>.</span><span class="sxs-lookup"><span data-stu-id="4bacb-112">For a non-linguistic comparison or support for result-based security decisions, the application should use a comparison method that accepts a <xref:System.StringComparison> value.</span></span> <span data-ttu-id="4bacb-113">Приложение должно передавать <xref:System.StringComparison.Ordinal>.</span><span class="sxs-lookup"><span data-stu-id="4bacb-113">The application should then pass <xref:System.StringComparison.Ordinal>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bacb-114">См. также</span><span class="sxs-lookup"><span data-stu-id="4bacb-114">See Also</span></span>  
 <xref:System.Array.Sort%2A?displayProperty=nameWithType>  
 <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType>  
 <xref:System.Collections.IComparer>  
 [<span data-ttu-id="4bacb-115">Выполнение строковых операций, не зависящих от языка и региональных параметров</span><span class="sxs-lookup"><span data-stu-id="4bacb-115">Performing Culture-Insensitive String Operations</span></span>](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)
