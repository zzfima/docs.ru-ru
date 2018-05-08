---
title: Метод EmitAssemblyCustomAttribute
ms.date: 03/30/2017
api_name:
- IALink.EmitAssemblyCustomAttribute
- EmitAssemblyCustomAttribute
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitAssemblyCustomAttribute
helpviewer_keywords:
- EmitAssemblyCustomAttribute method
ms.assetid: b72f5409-79af-4fa7-90a7-7630eec170f1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: daf2c3dcaf16e949f8770121d8324cbfe6c7d05b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="emitassemblycustomattribute-method"></a>Метод EmitAssemblyCustomAttribute
Вызов для установки настраиваемые атрибуты уровня сборки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT EmitAssemblyCustomAttribute(  
    mdAssembly   AssemblyID,  
    mdToken      FileToken,  
    mdToken      tkType,  
    void const*  pCustomValue,  
    DWORD        cbCustomValue,  
    BOOL         bSecurity,  
    BOOL         bAllowMulti  
) PURE;  
```  
  
#### <a name="parameters"></a>Параметры  
 `AssemblyID`  
 Идентификатор сборки.  
  
 `FileToken`  
 Файл, понижающий уровень атрибута. Может иметь значение NULL, если `AssemblyID` не указывает на несвязанный NETMODULE-файл.  
  
 `tkType`  
 Тип настраиваемого атрибута.  
  
 `pCustomValue`  
 Пользовательские данные значения.  
  
 `cbCustomValue`  
 Длина пользовательских данных значения.  
  
 `bSecurity`  
 Значение TRUE, если пользовательский атрибут имеет отношение к подписи сборки.  
  
 `bAllowMulti`  
 Значение TRUE, если несколько атрибутов, которые должны быть созданы.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK, если метод выполнен успешно.  
  
## <a name="requirements"></a>Требования  
 Требуется alink.h  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IALink](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [Интерфейс IALink2](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [API ALink](../../../../docs/framework/unmanaged-api/alink/index.md)
