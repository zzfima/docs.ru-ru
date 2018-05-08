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
ms.openlocfilehash: db818f638898da6379ce4dadfada8eccc3adeb12
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="strongnameerrorinfo-function"></a>Функция StrongNameErrorInfo
Возвращает последний код ошибки, вызванной одной из функций строгого имени.  
  
 Эта функция устарела.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT StrongNameErrorInfo ();   
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Последний код ошибки COM, заданный одной из функций строгого имени.  
  
## <a name="remarks"></a>Примечания  
 Большинство методов строгим именем возвращает простой `true` или `false` , указывающее успешное завершение. Используйте `StrongNameErrorInfo` функцию, чтобы извлечь значение HRESULT, указывающее последней ошибки, возникающие из функций строгого имени.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** StrongName.h  
  
 **Библиотека:** включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Строгое именование глобальные статические функции](http://msdn.microsoft.com/library/efa715df-e8cc-48f2-9ec4-26586f0dc8d0)
