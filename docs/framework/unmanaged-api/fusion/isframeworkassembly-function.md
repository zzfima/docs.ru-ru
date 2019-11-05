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
ms.openlocfilehash: e30b6f2d2254d2d107c4c82a2c5664850ce6ec23
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123071"
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
  
## <a name="remarks"></a>Заметки  
 Параметр `pwzAssemblyReference` — это указатель на символьную строку, содержащую имя сборки.  
  
 Если эта сборка является частью .NET Framework, параметр `pbIsFrameworkAssembly` будет содержать логическое значение `true`.  
  
 Если именованная сборка не является частью .NET Framework или если параметр `pwzAssemblyReference` не имеет имени сборки, `pbIsFrameworkAssembly` будет содержать логическое значение `false`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
## <a name="see-also"></a>См. также

- [Глобальные статические функции Fusion](fusion-global-static-functions.md)
