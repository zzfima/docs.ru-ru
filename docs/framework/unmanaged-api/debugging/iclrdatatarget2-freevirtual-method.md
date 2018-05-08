---
title: Метод ICLRDataTarget2::FreeVirtual
ms.date: 03/30/2017
api_name:
- ICLRDataTarget2.FreeVirtual
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget2::FreeVirtual
helpviewer_keywords:
- ICLRDataTarget::FreeVirtual method [.NET Framework debugging]
- FreeVirtual method [.NET Framework debugging]
ms.assetid: 26fb69f8-1467-4711-bd24-cb117c63938f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e7351dfb046653e4f3e20e0dc8a4bba8653ec36e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="iclrdatatarget2freevirtual-method"></a>Метод ICLRDataTarget2::FreeVirtual
Вызывается службами доступа к данным среды выполнения (CLR) для освобождения памяти, который ранее был выделен в адресное пространство целевого процесса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT FreeVirtual(  
    [in] CLRDATA_ADDRESS addr,  
    [in] ULONG32 size,  
    [in] ULONG32 typeFlags  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `addr`  
 [in] Объект `CLRDATA_ADDRESS` значение, которое определяет начальный адрес освобождаемой памяти.  
  
 `size`  
 [in] Размер в байтах для освобождения памяти.  
  
 `typeFlags`  
 [in] Флаги, управляющие освобождении памяти. В разделе Win32 `VirtualFree` функции.  
  
## <a name="remarks"></a>Примечания  
 `FreeVirtual` Метод служит логической программой-оболочкой для функции Win32 `VirtualFree` функции.  
  
 Этот метод реализуется модулем записи отладчика.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** ClrData.idl, ClrData.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICLRDataTarget2](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)  
 [Метод AllocVirtual](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-allocvirtual-method.md)
