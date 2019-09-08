---
title: Общие типы данных (справочник по неуправляемым интерфейсам API)
ms.date: 03/30/2017
ms.assetid: e4ab2c4c-9433-4eba-9e9a-096de406cafb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5b0a27eae744fb22c87634aaf6a0274a9825d981
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70776464"
---
# <a name="common-data-types-unmanaged-api-reference"></a>Общие типы данных (справочник по неуправляемым интерфейсам API)
В этом разделе перечислены простые типы данных, которые используются неуправляемыми API для платформы .NET Framework, определенными инструкциями C/C++ `typedef`. Эти типы данных, как правило, являются псевдонимами примитивных типов данных языка программирования C/C++. Как правило, значения этих типов данных непрозрачны, т. е. возвращаются конкретной функцией или методом таким образом, что могут быть переданы в другие функции или методы без изменений.  
  
|Тип данных|Определение|Определен в|Описание|  
|---------------|----------------|----------------|-----------------|  
|AppDomainID|`typedef UINT_PTR AppDomainID;`|corprof.h|Идентификатор домена приложения.|  
|AssemblyID|`typedef UINT_PTR AssemblyID;`|corprof.h|Идентификатор сборки.|  
|ClassID:|`typedef UINT_PTR ClassID;`|corprof.h|Идентификатор управляемого класса.|  
|CLRDATA_ADDRESS|`typedef ULONG64 CLRDATA_ADDRESS;`|клрдата. h|64-разрядный адрес памяти.|
|CLRDATA_ENUM|`typedef ULONG64 CLRDATA_ADDRESS;`|Недоступно|64-разрядный адрес памяти.|
|CONNID|`typedef DWORD CONNID;`|cordebug.h, mscoree.h|Идентификатор подключения для потока, подключенного к экземпляру Microsoft SQL Server.|  
|ContextID|`typedef UINT_PTR ContextID;`|corprof.h|Идентификатор контекста, связанного с определенным управляемым потоком.|  
|COR_PRF_ELT_INFO|`typedef UINT_PTR COR_PRF_ELT_INFO;`|corprof.h|Непрозрачный дескриптор, представляющий сведения об определенном кадре стека.|  
|COR_PRF_FRAME_INFO|`typedef UINT_PTR COR_PRF_FRAME_INFO;`|corprof.h|Непрозрачный дескриптор, который указывает на кадр стека. Допускается только при обратном вызове, к которому он передается.|  
|CORDB_ADDRESS|`typedef ULONG64 CORDB_ADDRESS;`|cordebug.h|Адрес в памяти.|  
|CORDB_CONTINUE_STATUS|`typedef DWORD CORDB_CONTINUE_STATUS;`|cordebug.h|Состояние продолжения.|  
|CORDB_REGISTER|`typedef ULONG64 CORDB_REGISTER;`|cordebug.h|Значение регистра ЦП.|
|FunctionID|`typedef UINT_PTR FunctionID;`|corprof.h|Идентификатор функции или метода.|  
|GCHandleID|`typedef UINT_PTR GCHandleID;`|corprof.h|Обработчик сборки мусора.|  
|мдмесоддеф|`typedef mdToken mdMethodDef;`|cordebug.h|Токен определения метода.|
|mdToken|`typedef UINT32 mdToken;`|corprof.h|Токен метаданных (строка в таблице метаданных).|  
|ModuleID|`typedef UINT_PTR ModuleID;`|corprof.h|Идентификатор модуля сборки.|  
|ObjectID|`typedef UINT_PTR ObjectID;`|corprof.h|Идентификатор объекта.|  
|PCCOR_SIGNATURE|`typedef SIZE_T PCCOR_SIGNATURE;`|cordebug.h|Указатель на подпись элемента или метаданных.|
|ProcessID|`typedef UINT_PTR ProcessID;`|corprof.h|Идентификатор управляемого процесса.|  
|ReJITID|`typedef UINT_PTR ReJITID;`|corprof.h|Идентификатор функции, откомпилированной по требованию.|  
|SIZE_T|`typedef ULONG_PTR SIZE_T;`|корсим. h|Указатель на 64-разрядный адрес памяти.|
|TASKID|`typedef UINT64 TASKID;`|cordebug.h, mscoree.h|Идентификатор экземпляра [ICLRTask](./hosting/iclrtask-interface.md) .|  
|ThreadID|`typedef UINT_PTR ThreadID;`|corprof.h|Идентификатор управляемого потока.|  
  
## <a name="see-also"></a>См. также

- [Справочник по неуправляемым API](index.md)
