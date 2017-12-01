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
# <a name="performing-culture-insensitive-string-operations-in-arrays"></a>Выполнение в массивах строковых операций, не зависящих от языка и региональных параметров
Перегруженные версии <xref:System.Array.Sort%2A?displayProperty=nameWithType> и <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType> методы выполняют операции сортировки язык и региональные параметры по умолчанию с помощью <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> свойство. Результат, возвращаемый этими методами меняется в зависимости от языка и региональных параметров, из-за различий в порядках сортировки. Чтобы зависел от языка и региональных параметров, используйте одну из перегрузок метода, принимающую `comparer` параметра. `comparer` Указывает <xref:System.Collections.IComparer> реализацию, которая используется при сравнении элементов в массиве. Для параметра, укажите пользовательский инвариантный класс сравнения, использующий <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>. Пример настраиваемого инвариантного класса сравнения предоставляется в подразделе «Использование класса SortedList» из [выполнение операций над строками в коллекциях без учета языка и региональных параметров](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-collections.md) раздела.  
  
 **Примечание** передачи **CultureInfo.InvariantCulture** для сравнения метод сравнения без учета языка и региональных параметров. Однако при этом не выполняется нелингвистическое сравнение, например для путей к файлам, разделов реестра и переменных среды. Также не поддерживается принятие решений по безопасности на основе результата сравнения. Для принятия решений системы безопасности на основе результатов или нелингвистическое сравнение, приложение должно использовать метод сравнения, который принимает <xref:System.StringComparison> значение. Приложение должно передавать <xref:System.StringComparison.Ordinal>.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Array.Sort%2A?displayProperty=nameWithType>  
 <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType>  
 <xref:System.Collections.IComparer>  
 [Выполнение строковых операций, не зависящих от языка и региональных параметров](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)
