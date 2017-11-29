---
title: "Перечисление CorMethodImpl"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorMethodImpl
api_location: mscoree.dll
api_type: COM
f1_keywords: CorMethodImpl
helpviewer_keywords: CorMethodImpl enumeration [.NET Framework metadata]
ms.assetid: ffbb3caf-20da-4a4b-8983-77376e72b990
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 85ee55c0d4ec0d3fb8c18dff570afefeb2eaf25e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
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
  
## <a name="members"></a>Члены  
  
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
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
