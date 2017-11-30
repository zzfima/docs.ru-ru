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
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1b4e040ed379cdbf43fbe8b2c4379fdd4dc781f2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="performing-culture-insensitive-string-operations-in-arrays"></a><span data-ttu-id="bf628-102">Выполнение в массивах строковых операций, не зависящих от языка и региональных параметров</span><span class="sxs-lookup"><span data-stu-id="bf628-102">Performing Culture-Insensitive String Operations in Arrays</span></span>
<span data-ttu-id="bf628-103">Перегруженные версии <xref:System.Array.Sort%2A?displayProperty=nameWithType> и <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType> методы выполняют операции сортировки язык и региональные параметры по умолчанию с помощью <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> свойство.</span><span class="sxs-lookup"><span data-stu-id="bf628-103">Overloads of the <xref:System.Array.Sort%2A?displayProperty=nameWithType> and <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType> methods perform culture-sensitive sorts by default using the <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="bf628-104">Результат, возвращаемый этими методами меняется в зависимости от языка и региональных параметров, из-за различий в порядках сортировки.</span><span class="sxs-lookup"><span data-stu-id="bf628-104">Culture-sensitive results returned by these methods can vary by culture due to differences in sort orders.</span></span> <span data-ttu-id="bf628-105">Чтобы зависел от языка и региональных параметров, используйте одну из перегрузок метода, принимающую `comparer` параметра.</span><span class="sxs-lookup"><span data-stu-id="bf628-105">To eliminate culture-sensitive behavior, use one of the overloads of this method that accepts a `comparer` parameter.</span></span> <span data-ttu-id="bf628-106">`comparer` Указывает <xref:System.Collections.IComparer> реализацию, которая используется при сравнении элементов в массиве.</span><span class="sxs-lookup"><span data-stu-id="bf628-106">The `comparer` parameter specifies the <xref:System.Collections.IComparer> implementation to use when comparing elements in the array.</span></span> <span data-ttu-id="bf628-107">Для параметра, укажите пользовательский инвариантный класс сравнения, использующий <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bf628-107">For the parameter, specify a custom invariant comparer class that uses <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="bf628-108">Пример настраиваемого инвариантного класса сравнения предоставляется в подразделе «Использование класса SortedList» из [выполнение операций над строками в коллекциях без учета языка и региональных параметров](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-collections.md) раздела.</span><span class="sxs-lookup"><span data-stu-id="bf628-108">An example of a custom invariant comparer class is provided in the "Using the SortedList Class" subtopic of the [Performing Culture-Insensitive String Operations in Collections](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-collections.md) topic.</span></span>  
  
 <span data-ttu-id="bf628-109">**Примечание** передачи **CultureInfo.InvariantCulture** для сравнения метод сравнения без учета языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="bf628-109">**Note** Passing **CultureInfo.InvariantCulture** to a comparison method does perform a culture-insensitive comparison.</span></span> <span data-ttu-id="bf628-110">Однако при этом не выполняется нелингвистическое сравнение, например для путей к файлам, разделов реестра и переменных среды.</span><span class="sxs-lookup"><span data-stu-id="bf628-110">However, it does not cause a non-linguistic comparison, for example, for file paths, registry keys, and environment variables.</span></span> <span data-ttu-id="bf628-111">Также не поддерживается принятие решений по безопасности на основе результата сравнения.</span><span class="sxs-lookup"><span data-stu-id="bf628-111">Neither does it support security decisions based on the comparison result.</span></span> <span data-ttu-id="bf628-112">Для принятия решений системы безопасности на основе результатов или нелингвистическое сравнение, приложение должно использовать метод сравнения, который принимает <xref:System.StringComparison> значение.</span><span class="sxs-lookup"><span data-stu-id="bf628-112">For a non-linguistic comparison or support for result-based security decisions, the application should use a comparison method that accepts a <xref:System.StringComparison> value.</span></span> <span data-ttu-id="bf628-113">Приложение должно передавать <xref:System.StringComparison.Ordinal>.</span><span class="sxs-lookup"><span data-stu-id="bf628-113">The application should then pass <xref:System.StringComparison.Ordinal>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf628-114">См. также</span><span class="sxs-lookup"><span data-stu-id="bf628-114">See Also</span></span>  
 <xref:System.Array.Sort%2A?displayProperty=nameWithType>  
 <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType>  
 <xref:System.Collections.IComparer>  
 [<span data-ttu-id="bf628-115">Выполнение строковых операций, не зависящих от языка и региональных параметров</span><span class="sxs-lookup"><span data-stu-id="bf628-115">Performing Culture-Insensitive String Operations</span></span>](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)
