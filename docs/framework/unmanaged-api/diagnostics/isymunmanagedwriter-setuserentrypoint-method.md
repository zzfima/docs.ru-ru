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
ms.openlocfilehash: 951fc10a4560e0b4e256312017cdcd9a389f17f5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427814"
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
 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
