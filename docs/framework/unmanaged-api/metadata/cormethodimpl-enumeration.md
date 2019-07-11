---
title: Перечисление CorMethodImpl
ms.date: 03/30/2017
api_name:
- CorMethodImpl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorMethodImpl
helpviewer_keywords:
- CorMethodImpl enumeration [.NET Framework metadata]
ms.assetid: ffbb3caf-20da-4a4b-8983-77376e72b990
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0c88c12646a13e5a24f2475bd2db04c8c831141c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781757"
---
# <a name="cormethodimpl-enumeration"></a>Перечисление CorMethodImpl
Содержит значения, описывающие возможности реализации метода.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum CorMethodImpl {  
  
    miCodeTypeMask      =   0x0003,  
    miIL                =   0x0000,  
    miNative            =   0x0001,  
    miOPTIL             =   0x0002,  
    miRuntime           =   0x0003,  
  
    miManagedMask       =   0x0004,  
    miUnmanaged         =   0x0004,  
    miManaged           =   0x0000,  
  
    miForwardRef        =   0x0010,  
    miPreserveSig       =   0x0080,  
  
    miInternalCall      =   0x1000,  
    miSynchronized      =   0x0020,  
    miNoInlining        =   0x0008,  
    miAggressiveInlining =  0x0100,  
    miNoOptimization     =  0x0040,  
    miMaxMethodImplVal  =   0xffff  
  
} CorMethodImpl;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`miCodeTypeMask`|Флаги, описывающие тип кода.|  
|`miIL`|Указывает, что метод реализуется на промежуточном языке Майкрософт (MSIL).|  
|`miNative`|Указывает, что для метода используется стандартная реализация.|  
|`miOPTIL`|Указывает, что метод реализуется OPTIL.|  
|`miRuntime`|Указывает, что реализация метода предоставляется средой CLR.|  
|`miManagedMask`|Флаги, указывающие ли управляемый или неуправляемый код.|  
|`miUnmanaged`|Указывает, что реализация метода является неуправляемым.|  
|`miManaged`|Указывает, что реализация метода является управляемым.|  
|`miForwardRef`|Указывает, что этот метод определен. Этот флаг используется в основном в сценариях слияния.|  
|`miPreserveSig`|Указывает, что сигнатура метода не может быть изменена для преобразования HRESULT.|  
|`miInternalCall`|Зарезервировано для внутреннего использования средой CLR.|  
|`miSynchronized`|Указывает, что метод является однопоточным выполнение основной части.|  
|`miNoInlining`|Указывает, что метод нельзя выполнять как встроенный.|  
|`miAggressiveInlining`|Указывает, что метод должен выполняться как встроенный, если это возможно.|  
|`miNoOptimization`|Указывает, что метод не должен быть оптимизирован.|  
|`miMaxMethodImplVal`|Максимальное допустимое значение для `CorMethodImpl`.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorHdr.h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
