---
title: "Маршалинг строк"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- marshaling, samples
- platform invoke, marshaling data
- data marshaling, strings
- data marshaling, samples
- data marshaling, platform invoke
- marshaling. strings
- marshaling, platform invoke
- sample applications [.NET Framework], marshaling strings
ms.assetid: e21b078b-70fb-4905-be26-c097ab2433ff
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 89dace5ba946f2c6bd1384f23ffcff797e99bdd4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="marshaling-strings"></a>Маршалинг строк
При вызове неуправляемого кода копируются строковые аргументы, и при необходимости выполняется преобразование этих аргументов из формата .NET Framework (Юникод) в неуправляемый формат (ANSI). Так как управляемые строки являются неизменяемыми, то при вызове неуправляемого кода они не копируются обратно из неуправляемой памяти в управляемую память при возврате из функции.  
  
 В таблице ниже представлены варианты маршалинга строк, описано их использование и приведена ссылка на соответствующий пример кода .NET Framework.  
  
|Строка|Описание|Пример|  
|------------|-----------------|------------|  
|По значению.|Передает строки в качестве параметров In.|[MsgBox](../../../docs/framework/interop/msgbox-sample.md)|  
|Как результат.|Возвращает строки из неуправляемого кода.|[Строки](http://msdn.microsoft.com/en-us/be9e82a3-dc95-4aaa-9396-61b66e467e02)|  
|По ссылке.|Передает строки в качестве параметров In/Out с помощью <xref:System.Text.StringBuilder>.|[Buffers](http://msdn.microsoft.com/en-us/e30d36e8-d7c4-4936-916a-8fdbe4d9ffd5)|  
|В структуре по значению.|Передает строки в структуре, которая является параметром In.|[Структуры](http://msdn.microsoft.com/en-us/96a62265-dcf9-4608-bc0a-1f762ab9f48e)|  
|В структуре по ссылке **(char\*)**.|Передает строки в структуре, которая является параметром In/Out. Неуправляемая функция ожидает указатель на символьный буфер, и размер буфера является членом структуры.|[Строки](http://msdn.microsoft.com/en-us/be9e82a3-dc95-4aaa-9396-61b66e467e02)|  
|В структуре по ссылке **(char[])**.|Передает строки в структуре, которая является параметром In/Out. Неуправляемая функция ожидает внедренный символьный буфер.|[OSInfo](http://msdn.microsoft.com/en-us/69d89067-507b-41fe-859d-30bf3ff29455)|  
|В классе по значению **(char\*)**.|Передает строки в классе (класс является параметром In/Out). Неуправляемая функция ожидает указатель на символьный буфер.|[OpenFileDlg](http://msdn.microsoft.com/en-us/b7dea792-cb92-4baf-ac7b-6a24803e6c75)|  
|В классе по значению **(char[])**.|Передает строки в классе (класс является параметром In/Out). Неуправляемая функция ожидает внедренный символьный буфер.|[OSInfo](http://msdn.microsoft.com/en-us/69d89067-507b-41fe-859d-30bf3ff29455)|  
|Как массив строк по значению.|Создает массив строк, который передается по значению.|[Массивы](../../../docs/framework/interop/marshaling-different-types-of-arrays.md)|  
|Как массив структур, содержащих строки по значению.|Создает массив структур, содержащих строки. Массив передается по значению.|[Массивы](../../../docs/framework/interop/marshaling-different-types-of-arrays.md)|  
  
## <a name="see-also"></a>См. также  
 [Маршалинг данных при вызове неуправляемого кода](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)  
 [Типы данных вызовов неуправляемого кода](http://msdn.microsoft.com/en-us/16014d9f-d6bd-481e-83f0-df11377c550f)  
 [Маршалинг классов, структур и объединений](../../../docs/framework/interop/marshaling-classes-structures-and-unions.md)  
 [Маршалинг массивов типов](http://msdn.microsoft.com/en-us/049b1c1b-228f-4445-88ec-91bc7fd4b1e8)  
 [Различные примеры маршалинга](http://msdn.microsoft.com/en-us/a915c948-54e9-4d0f-a525-95a77fd8ed70)
