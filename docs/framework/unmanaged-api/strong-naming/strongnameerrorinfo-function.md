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
ms.openlocfilehash: 021fa1668247bc59a4412d2b5f4bac3f5ee8cc6b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799114"
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
 Большинство методов со строгим именем возвращают простой `true` или `false` индикатор успешного завершения. `StrongNameErrorInfo` Используйте функцию, чтобы получить значение HRESULT, указывающее последнюю ошибку, созданную функциями строгого имени.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок.** StrongName. h  
  
 **Библиотечная** Включается в качестве ресурса в библиотеку MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
