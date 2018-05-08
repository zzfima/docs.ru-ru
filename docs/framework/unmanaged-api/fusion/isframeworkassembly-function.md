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
ms.openlocfilehash: c3fd130759ab11b54b597d5c099c33dab93070ae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="isframeworkassembly-function"></a>Функция IsFrameworkAssembly
Возвращает значение, указывающее, является ли указанная сборка управляемой.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT IsFrameworkAssembly (  
    [in]  LPCWSTR pwzAssemblyReference,  
    [out] LPBOOL  pbIsFrameworkAssembly,  
    [in]  LPWSTR  pwzFrameworkAssemblyIdentity,  
    [in]  LPDWORD pccSize  
 );  
```  
  
#### <a name="parameters"></a>Параметры  
 `pwzAssemblyReference`  
 [in] Имя сборки для проверки.  
  
 `pbIsFrameworkAssembly`  
 [out] Логическое значение, указывающее, управляется ли сборки.  
  
 `pwzFrameworkAssemblyIdentity`  
 [in] Uncanonicalized строка, которая содержит уникальный идентификатор сборки.  
  
 `pccSize`  
 [входной] Размер `pwzFrameworkAssemblyIdentity`.  
  
## <a name="remarks"></a>Примечания  
 `pwzAssemblyReference` Параметр является указателем на строку символов, содержащая имя сборки.  
  
 Если эта сборка является частью платформы .NET Framework, `pbIsFrameworkAssembly` параметр будет содержать значение типа Boolean `true`.  
  
 Если для этого именованную сборку не является частью .NET Framework или `pwzAssemblyReference` параметр не задает имя сборки, `pbIsFrameworkAssembly` будет содержать значение типа Boolean `false`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
## <a name="see-also"></a>См. также  
 [Глобальные статические функции Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
