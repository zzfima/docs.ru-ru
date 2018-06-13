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
ms.openlocfilehash: 4bb91423b2eaeda7d945cf14553609fd33ce9b0c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443493"
---
# <a name="cormethodimpl-enumeration"></a>Перечисление CorMethodImpl
Содержит значения, описывающие возможности реализации метода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
|`miIL`|Указывает, что реализация метода промежуточного языка Майкрософт (MSIL).|  
|`miNative`|Указывает, что для метода используется стандартная реализация.|  
|`miOPTIL`|Указывает, что реализация метода OPTIL.|  
|`miRuntime`|Указывает, что реализация метода обеспечивается средой CLR.|  
|`miManagedMask`|Флаги, указывающие, является ли код является управляемым или неуправляемым.|  
|`miUnmanaged`|Указывает, что реализация метода является неуправляемым.|  
|`miManaged`|Указывает, что метод реализуется как управляемый.|  
|`miForwardRef`|Указывает, что метод был определен. Этот флаг используется главным образом в сценариях слияния.|  
|`miPreserveSig`|Указывает, что подпись метода не может быть изменена для преобразования HRESULT.|  
|`miInternalCall`|Зарезервировано для внутреннего использования средой CLR.|  
|`miSynchronized`|Указывает, что метод является однопотоковым выполнение основной части.|  
|`miNoInlining`|Указывает, что метод нельзя выполнять как встроенный.|  
|`miAggressiveInlining`|Указывает, что метод должен быть встроенным по возможности.|  
|`miNoOptimization`|Указывает, что метод не должен быть оптимизирован.|  
|`miMaxMethodImplVal`|Максимальное допустимое значение для `CorMethodImpl`.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorHdr.h  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
