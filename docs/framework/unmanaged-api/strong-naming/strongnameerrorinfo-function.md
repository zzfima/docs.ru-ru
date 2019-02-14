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
ms.openlocfilehash: b3d7555ec5b87957ff1c8e085a4c3ac44c660b0c
ms.sourcegitcommit: af0a22a4eb11bbcd33baec49150d551955b50a16
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2019
ms.locfileid: "56260820"
---
# <a name="strongnameerrorinfo-function"></a>Функция StrongNameErrorInfo
Получает код последней ошибки, вызванной одной из функций строгого имени.  
  
 Эта функция является устаревшей.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
  
