---
title: Маршалинг строк
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 52a78e0c3969e879bf2fd1b1f5c41b2caac2ba11
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33391125"
---
# <a name="marshaling-strings"></a>Маршалинг строк
При вызове неуправляемого кода копируются строковые аргументы, и при необходимости выполняется преобразование этих аргументов из формата .NET Framework (Юникод) в неуправляемый формат (ANSI). Так как управляемые строки являются неизменяемыми, то при вызове неуправляемого кода они не копируются обратно из неуправляемой памяти в управляемую память при возврате из функции.  
  
 В таблице ниже представлены варианты маршалинга строк, описано их использование и приведена ссылка на соответствующий пример кода .NET Framework.  
  
|String|Описание:|Пример|  
|------------|-----------------|------------|  
|По значению.|Передает строки в качестве параметров In.|[MsgBox](msgbox-sample.md)|  
|Как результат.|Возвращает строки из неуправляемого кода.|[Строки](https://msdn.microsoft.com/library/be9e82a3-dc95-4aaa-9396-61b66e467e02(v=vs.100))|  
|По ссылке.|Передает строки в качестве параметров In/Out с помощью <xref:System.Text.StringBuilder>.|[Buffers](https://msdn.microsoft.com/library/e30d36e8-d7c4-4936-916a-8fdbe4d9ffd5(v=vs.100))|  
|В структуре по значению.|Передает строки в структуре, которая является параметром In.|[Структуры](https://msdn.microsoft.com/library/96a62265-dcf9-4608-bc0a-1f762ab9f48e(v=vs.100))|  
|В структуре по ссылке **(char\*)**.|Передает строки в структуре, которая является параметром In/Out. Неуправляемая функция ожидает указатель на символьный буфер, и размер буфера является членом структуры.|[Строки](https://msdn.microsoft.com/library/be9e82a3-dc95-4aaa-9396-61b66e467e02(v=vs.100))|  
|В структуре по ссылке **(char[])**.|Передает строки в структуре, которая является параметром In/Out. Неуправляемая функция ожидает внедренный символьный буфер.|[OSInfo](https://msdn.microsoft.com/library/69d89067-507b-41fe-859d-30bf3ff29455(v=vs.100))|  
|В классе по значению **(char\*)**.|Передает строки в классе (класс является параметром In/Out). Неуправляемая функция ожидает указатель на символьный буфер.|[OpenFileDlg](https://msdn.microsoft.com/library/b7dea792-cb92-4baf-ac7b-6a24803e6c75(v=vs.100))|  
|В классе по значению **(char[])**.|Передает строки в классе (класс является параметром In/Out). Неуправляемая функция ожидает внедренный символьный буфер.|[OSInfo](https://msdn.microsoft.com/library/69d89067-507b-41fe-859d-30bf3ff29455(v=vs.100))|  
|Как массив строк по значению.|Создает массив строк, который передается по значению.|[Массивы](marshaling-different-types-of-arrays.md)|  
|Как массив структур, содержащих строки по значению.|Создает массив структур, содержащих строки. Массив передается по значению.|[Массивы](marshaling-different-types-of-arrays.md)|  
  
## <a name="see-also"></a>См. также  
 [Маршалинг данных при вызове неуправляемого кода](marshaling-data-with-platform-invoke.md)  
 [Типы данных в вызове неуправляемого кода](https://msdn.microsoft.com/library/16014d9f-d6bd-481e-83f0-df11377c550f(v=vs.100))  
 [Маршалинг классов, структур и объединений](marshaling-classes-structures-and-unions.md)  
 [Маршалинг массивов типов](https://msdn.microsoft.com/library/049b1c1b-228f-4445-88ec-91bc7fd4b1e8(v=vs.100))  
 [Различные примеры маршалинга](https://msdn.microsoft.com/library/a915c948-54e9-4d0f-a525-95a77fd8ed70(v=vs.100))
