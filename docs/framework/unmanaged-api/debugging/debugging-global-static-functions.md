---
title: "Глобальные статические функции отладки"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- global static functions [.NET Framework debugging]
- debugging global static functions [.NET Framework]
- unmanaged global static functions [.NET Framework], debugging
ms.assetid: efc64414-77c3-48d0-881a-8594ed416aad
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ad5d3ef689a251ea4b154afc5d1bfb387388ddb3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="debugging-global-static-functions"></a>Глобальные статические функции отладки
В этом разделе описываются неуправляемые глобальные статистические функции, которые используют API отладки.  
  
## <a name="in-this-section"></a>Содержание  
 [Функция _EFN_GetManagedExcepStack](../../../../docs/framework/unmanaged-api/debugging/efn-getmanagedexcepstack-function.md)  
 Учитывая адрес объекта управляемого исключения, возвращает строковую версию трассировки стека, содержащейся внутри.  
  
 [Функция _EFN_GetManagedObjectFieldInfo](../../../../docs/framework/unmanaged-api/debugging/efn-getmanagedobjectfieldinfo-function.md)  
 Возвращает смещение от начала объекта до поля и значение поля, используя предоставленный указатель объекта и имя поля.  
  
 [Функция _EFN_GetManagedObjectName](../../../../docs/framework/unmanaged-api/debugging/efn-getmanagedobjectname-function.md)  
 Получает имя типа с помощью предоставленного указателя управляемого объекта.  
  
 [Функция _EFN_StackTrace](../../../../docs/framework/unmanaged-api/debugging/efn-stacktrace-function.md)  
 Предоставляет текстовое представление трассировки управляемого стека и массив записей `CONTEXT`, по одной для каждого перехода между неуправляемым и управляемым кодом.  
  
 [Функция CLRDataCreateInstance](../../../../docs/framework/unmanaged-api/debugging/clrdatacreateinstance-function.md)  
 Вызывается службами доступа к данным среды CLR для создания указанного объекта интерфейса для заданного целевого процесса.  
  
 [Указатель функции Pfn_clrdatacreateinstance](../../../../docs/framework/unmanaged-api/debugging/pfn-clrdatacreateinstance-function-pointer.md)  
 Указывает на функцию, вызываемую службами доступа к данным среды CLR, чтобы создать указанный объект интерфейса для заданного целевого процесса.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Компонентные классы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)  
  
 [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
  
 [Перечисления отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
  
 [Структуры отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
