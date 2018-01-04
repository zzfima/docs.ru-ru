---
title: "Функция LoadFromHistory (WPF Справочник по неуправляемым API)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: cpp
api_name: LoadFromHistory
api_location: PresentationHost_v0400.dll
ms.assetid: d037c062-a911-4949-b251-ccd3e48b1d17
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6eca1c30664e381101b6e51c1347341432a042b2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="loadfromhistory-function-wpf-unmanaged-api-reference"></a>Функция LoadFromHistory (WPF Справочник по неуправляемым API)
Этот API поддерживает инфраструктуру Windows Presentation Foundation (WPF) и не предназначен для использования непосредственно из программного кода.  
  
 Используется инфраструктурой Windows Presentation Foundation (WPF) для управления windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT LoadFromHistory_export(  
        IStream* pHistoryStream,   
        IBindCtx* pBindCtx  
)  
```  
  
#### <a name="parameters"></a>Параметры  
 pHistoryStream  
 Указатель на поток данных журнала.  
  
 pBindCtx  
 Указатель на контекст привязки.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **БИБЛИОТЕКА DLL:**  
  
 В платформе .NET Framework 3.0 и 3.5: PresentationHostDLL.dll  
  
 В .NET Framework 4 и более поздних версий: PresentationHost_v0400.dll  
  
 **Версия платформы .NET framework:**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по неуправляемым API WPF](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)
