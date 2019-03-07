---
title: Функция IsFrameworkAssembly
ms.date: 03/30/2017
api_name:
- IsFrameworkAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IsFrameworkAssembly
helpviewer_keywords:
- IsFrameworkAssembly function [.NET Framework fusion]
ms.assetid: b0c6f19b-d4fd-4971-88f0-12ffb5793da3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d0fb4c98ff2c8b071f05b42aefed61485001e97f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57480329"
---
# <a name="isframeworkassembly-function"></a>Функция IsFrameworkAssembly
Получает значение, указывающее, управляется ли указанная сборка.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT IsFrameworkAssembly (  
    [in]  LPCWSTR pwzAssemblyReference,  
    [out] LPBOOL  pbIsFrameworkAssembly,  
    [in]  LPWSTR  pwzFrameworkAssemblyIdentity,  
    [in]  LPDWORD pccSize  
 );  
```  
  
## <a name="parameters"></a>Параметры  
 `pwzAssemblyReference`  
 [in] Имя сборки.  
  
 `pbIsFrameworkAssembly`  
 [out] Логическое значение, указывающее, управляется ли сборка.  
  
 `pwzFrameworkAssemblyIdentity`  
 [in] Это uncanonicalized строка, содержащая уникальный идентификатор сборки.  
  
 `pccSize`  
 [входной] Размер `pwzFrameworkAssemblyIdentity`.  
  
## <a name="remarks"></a>Примечания  
 `pwzAssemblyReference` Параметр является указателем на строку символов, содержащая имя сборки.  
  
 Если эта сборка является частью .NET Framework, `pbIsFrameworkAssembly` параметр будет содержать значение типа Boolean `true`.  
  
 Если для этого именованную сборку не является частью платформы .NET Framework или `pwzAssemblyReference` параметр не задает имя сборки, `pbIsFrameworkAssembly` будет содержать значение типа Boolean `false`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
## <a name="see-also"></a>См. также
- [Глобальные статические функции Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
