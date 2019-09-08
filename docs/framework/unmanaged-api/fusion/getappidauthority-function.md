---
title: Функция GetAppIdAuthority
ms.date: 03/30/2017
api_name:
- GetAppIdAuthority
api_location:
- fusion.dll
- clr.dll
api_type:
- COM
f1_keywords:
- GetAppIdAuthority
helpviewer_keywords:
- GetAppIdAuthority function [.NET Framework fusion]
ms.assetid: 9f968dad-0d09-47fb-bebc-94c39a0d16ad
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8471610008bee02c7cc4e7654b21d6aca5dcf53a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796284"
---
# <a name="getappidauthority-function"></a>Функция GetAppIdAuthority
Возвращает указатель на экземпляр [иаппидаусорити](iappidauthority-interface.md) , который управляет ключами для удостоверений приложений и ссылок.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetAppIdAuthority (  
    [out] IAppIdAuthority **ppIAppIdAuthority  
 );  
```  
  
## <a name="parameters"></a>Параметры  
 `ppIAppIdAuthority`  
 заполняет Возвращаемый `IAppIdAuthority` указатель.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок.** Изоляция. h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IAppIdAuthority](iappidauthority-interface.md)
- [Глобальные статические функции Fusion](fusion-global-static-functions.md)
