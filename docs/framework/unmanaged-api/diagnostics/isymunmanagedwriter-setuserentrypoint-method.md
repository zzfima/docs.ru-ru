---
title: Метод ISymUnmanagedWriter::SetUserEntryPoint
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetUserEntryPoint
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetUserEntryPoint
helpviewer_keywords:
- ISymUnmanagedWriter::SetUserEntryPoint method [.NET Framework debugging]
- SetUserEntryPoint method [.NET Framework debugging]
ms.assetid: d4dcc575-3ac8-4453-9be1-2b24f47363d7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 11dc050e2fe16a64db4ac95bb1386e2d90535e81
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/11/2019
ms.locfileid: "70895021"
---
# <a name="isymunmanagedwritersetuserentrypoint-method"></a>Метод ISymUnmanagedWriter::SetUserEntryPoint
Задает определяемый пользователем метод, являющийся точкой входа для этого модуля. Например, эта точка входа может быть основным методом пользователя вместо заглушек, созданной компилятором до Main.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetUserEntryPoint(  
    [in] mdMethodDef entryMethod);  
```  
  
## <a name="parameters"></a>Параметры  
 `entryMethod`  
 окне Токен метаданных для метода, который является точкой входа пользователя.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если метод выполнен. в противном случае — E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок.** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
