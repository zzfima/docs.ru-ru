---
title: Функция StrongNameErrorInfo
ms.date: 03/30/2017
api_name:
- StrongNameErrorInfo
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameErrorInfo
helpviewer_keywords:
- StrongNameErrorInfo function [.NET Framework strong naming]
ms.assetid: e91bf8c3-7c26-4732-938e-2e5b04abfc99
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a6f495500b087b9e24936acd414f1aff463d7f64
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781076"
---
# <a name="strongnameerrorinfo-function"></a>Функция StrongNameErrorInfo
Получает код последней ошибки, вызванной одной из функций строгого имени.  
  
 Эта функция является устаревшей.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT StrongNameErrorInfo ();   
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Последний код ошибки COM, заданный одной из функций строгого имени.  
  
## <a name="remarks"></a>Примечания  
 Большинство методов строгого имени возврата простой `true` или `false` значение, указывающее на успешное завершение. Используйте `StrongNameErrorInfo` функции для получения значение HRESULT, указывающее последней ошибки, возникшей при функций строгого имени.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** StrongName.h  
  
 **Библиотека:** Включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
