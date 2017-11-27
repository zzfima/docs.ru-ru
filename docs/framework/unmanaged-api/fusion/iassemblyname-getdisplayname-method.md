---
title: "Метод IAssemblyName::GetDisplayName"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IAssemblyName.GetDisplayName
api_location: fusion.dll
api_type: COM
f1_keywords: IAssemblyName::GetDisplayName
helpviewer_keywords:
- GetDisplayName method, IAssemblyName interface [.NET Framework fusion]
- IAssemblyName::GetDisplayName method [.NET Framework fusion]
ms.assetid: 9a26547a-9a34-4284-a463-78a7d4b496cf
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 810192848e15a200a4b2eb33eaf60ddbd7c7c607
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iassemblynamegetdisplayname-method"></a>Метод IAssemblyName::GetDisplayName
Возвращает понятное имя сборки, упоминаемой в этом [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetDisplayName (  
        [out]      LPOLESTR  szDisplayName,  
        [in, out]  LPDWORD   pccDisplayName,  
        [in]       DWORD     dwDisplayFlags  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `szDisplayName`  
 [out] Строковый буфер, который содержит имя сборки, на которую указывает ссылка.  
  
 `pccDisplayName`  
 [in, out] Размер `szDisplayName` из расширенных символов, включая символ завершения null.  
  
 `dwDisplayFlags`  
 [in] Побитовое сочетание [ASM_DISPLAY_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-display-flags-enumeration.md) значения, которые влияют на возможности `szDisplayName`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Fusion.h  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [IAssemblyName-интерфейс](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)  
 [Перечисления Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
