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
ms.openlocfilehash: 269e3702c21532f377735ba6087abb1603dde4f7
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796314"
---
# <a name="isframeworkassembly-function"></a>Функция IsFrameworkAssembly
Возвращает значение, указывающее, является ли указанная сборка управляемой.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT IsFrameworkAssembly (  
    [in]  LPCWSTR pwzAssemblyReference,  
    [out] LPBOOL  pbIsFrameworkAssembly,  
    [in]  LPWSTR  pwzFrameworkAssemblyIdentity,  
    [in]  LPDWORD pccSize  
 );  
```  
  
## <a name="parameters"></a>Параметры  
 `pwzAssemblyReference`  
 окне Имя проверяемой сборки.  
  
 `pbIsFrameworkAssembly`  
 заполняет Логическое значение, указывающее, является ли сборка управляемой.  
  
 `pwzFrameworkAssemblyIdentity`  
 окне Неканоническая строка, содержащая уникальный идентификатор сборки.  
  
 `pccSize`  
 [входной] Размер `pwzFrameworkAssemblyIdentity`.  
  
## <a name="remarks"></a>Примечания  
 `pwzAssemblyReference` Параметр является указателем на символьную строку, содержащую имя сборки.  
  
 Если эта сборка является частью .NET Framework, `pbIsFrameworkAssembly` параметр будет содержать логическое `true`значение.  
  
 Если именованная сборка не является частью .NET Framework или если `pwzAssemblyReference` параметр не имеет имени сборки, `pbIsFrameworkAssembly` то будет `false`содержать логическое значение.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
## <a name="see-also"></a>См. также

- [Глобальные статические функции Fusion](fusion-global-static-functions.md)
