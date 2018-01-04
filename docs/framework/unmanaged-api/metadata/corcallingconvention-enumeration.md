---
title: "Перечисление CorCallingConvention"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorCallingConvention
api_location: mscoree.dll
api_type: COM
f1_keywords: CorCallingConvention
helpviewer_keywords: CorCallingConvention enumeration [.NET Framework metadata]
ms.assetid: 69156fbf-7219-43bf-b4b8-b13f1a2fcb86
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 154fbcc393bb56ab2c249a4928a4451dced9761a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="corcallingconvention-enumeration"></a>Перечисление CorCallingConvention
Содержит значения, описывающие типы соглашений о вызовах, выполняемых в управляемом коде.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef enum CorCallingConvention  
{  
    IMAGE_CEE_CS_CALLCONV_DEFAULT       = 0x0,  
  
    IMAGE_CEE_CS_CALLCONV_VARARG        = 0x5,  
    IMAGE_CEE_CS_CALLCONV_FIELD         = 0x6,  
    IMAGE_CEE_CS_CALLCONV_LOCAL_SIG     = 0x7,  
    IMAGE_CEE_CS_CALLCONV_PROPERTY      = 0x8,  
    IMAGE_CEE_CS_CALLCONV_UNMGD         = 0x9,  
    IMAGE_CEE_CS_CALLCONV_GENERICINST   = 0xa,  
    IMAGE_CEE_CS_CALLCONV_NATIVEVARARG  = 0xb,  
    IMAGE_CEE_CS_CALLCONV_MAX           = 0xc,  
  
    IMAGE_CEE_CS_CALLCONV_MASK          = 0x0f,  
    IMAGE_CEE_CS_CALLCONV_HASTHIS       = 0x20,  
    IMAGE_CEE_CS_CALLCONV_EXPLICITTHIS  = 0x40,  
    IMAGE_CEE_CS_CALLCONV_GENERIC       = 0x10  
  
} CorCallingConvention;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание:|  
|------------|-----------------|  
|`IMAGE_CEE_CS_CALLCONV_DEFAULT`|Указывает значение по умолчанию, соглашение о вызовах.|  
|`IMAGE_CEE_CS_CALLCONV_VARARG`|Указывает, что метод принимает переменное число параметров.|  
|`IMAGE_CEE_CS_CALLCONV_FIELD`|Указывает, что вызов к полю.|  
|`IMAGE_CEE_CS_CALLCONV_LOCAL_SIG`|Указывает, что вызов локального метода.|  
|`IMAGE_CEE_CS_CALLCONV_PROPERTY`|Указывает, что вызов к свойству.|  
|`IMAGE_CEE_CS_CALLCONV_UNMGD`|Указывает, что вызов является неуправляемым.|  
|`IMAGE_CEE_CS_CALLCONV_GENERICINST`|Указывает на создание экземпляров универсального метода.|  
|`IMAGE_CEE_CS_CALLCONV_NATIVEVARARG`|Указывает метод, который принимает переменное число параметров вызова PInvoke 64-разрядной.|  
|`IMAGE_CEE_CS_CALLCONV_MAX`|Описывает недопустимое 4-разрядное значение.|  
|`IMAGE_CEE_CS_CALLCONV_MASK`|Указывает, что соглашение о вызове описывается четырьмя младшими битами.|  
|`IMAGE_CEE_CS_CALLCONV_HASTHIS`|Указывает, что старшие биты описывают `this` параметра.|  
|`IMAGE_CEE_CS_CALLCONV_EXPLICITTHIS`|Указывает, что `this` параметр четко описаны в сигнатуре.|  
|`IMAGE_CEE_CS_CALLCONV_GENERIC`|Указывает сигнатуру универсального метода с явной количество аргументов типа. Это предшествует обычное число параметров.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorHdr.h  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
