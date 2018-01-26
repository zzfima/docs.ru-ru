---
title: "Общие типы данных (справочник по неуправляемым интерфейсам API)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: e4ab2c4c-9433-4eba-9e9a-096de406cafb
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a565ec6ded0a82ed4ab3c0fd03b082d996369ddc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="common-data-types-unmanaged-api-reference"></a>Общие типы данных (справочник по неуправляемым интерфейсам API)
В этом разделе перечислены простые типы данных, которые используются неуправляемыми API для платформы .NET Framework, определенными инструкциями C/C++ `typedef`. Эти типы данных, как правило, являются псевдонимами примитивных типов данных языка программирования C/C++. Как правило, значения этих типов данных непрозрачны, т. е. возвращаются конкретной функцией или методом таким образом, что могут быть переданы в другие функции или методы без изменений.  
  
|Тип данных|Определение|Определен в|Описание|  
|---------------|----------------|----------------|-----------------|  
|AppDomainID|`typedef UINT_PTR AppDomainID;`|corprof.h|Идентификатор домена приложения.|  
|AssemblyID|`typedef UINT_PTR AssemblyID;`|corprof.h|Идентификатор сборки.|  
|ClassID|`typedef UINT_PTR ClassID;`|corprof.h|Идентификатор управляемого класса.|  
|CONNID|`typedef DWORD CONNID;`|cordebug.h, mscoree.h|Идентификатор подключения для потока, подключенного к экземпляру Microsoft SQL Server.|  
|ContextID|`typedef UINT_PTR ContextID;`|corprof.h|Идентификатор контекста, связанного с определенным управляемым потоком.|  
|COR_PRF_ELT_INFO|`typedef UINT_PTR COR_PRF_ELT_INFO;`|corprof.h|Непрозрачный дескриптор, представляющий сведения об определенном кадре стека.|  
|COR_PRF_FRAME_INFO|`typedef UINT_PTR COR_PRF_FRAME_INFO;`|corprof.h|Непрозрачный дескриптор, который указывает на кадр стека. Допускается только при обратном вызове, к которому он передается.|  
|CORDB_ADDRESS|`typedef ULONG64 CORDB_ADDRESS;`|cordebug.h|Адрес в памяти.|  
|CORDB_CONTINUE_STATUS|`typedef DWORD CORDB_CONTINUE_STATUS;`|cordebug.h|Состояние продолжения.|  
|CORDB_REGISTER|`typedef ULONG64 CORDB_REGISTER;`|cordebug.h|Значение регистра ЦП.|  
|FunctionID|`typedef UINT_PTR FunctionID;`|corprof.h|Идентификатор функции или метода.|  
|GCHandleID|`typedef UINT_PTR GCHandleID;`|corprof.h|Обработчик сборки мусора.|  
|mdToken|`typedef UINT32 mdToken;`|corprof.h|Токен метаданных (строка в таблице метаданных).|  
|ModuleID|`typedef UINT_PTR ModuleID;`|corprof.h|Идентификатор модуля сборки.|  
|ObjectID|`typedef UINT_PTR ObjectID;`|corprof.h|Идентификатор объекта.|  
|ProcessID|`typedef UINT_PTR ProcessID;`|corprof.h|Идентификатор управляемого процесса.|  
|ReJITID|`typedef UINT_PTR ReJITID;`|corprof.h|Идентификатор функции, откомпилированной по требованию.|  
|TASKID|`typedef UINT64 TASKID;`|cordebug.h, mscoree.h|Идентификатор [ICLRTask](../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) экземпляра.|  
|ThreadID|`typedef UINT_PTR ThreadID;`|corprof.h|Идентификатор управляемого потока.|  
  
## <a name="see-also"></a>См. также  
 [Справочник по неуправляемым API](../../../docs/framework/unmanaged-api/index.md)
