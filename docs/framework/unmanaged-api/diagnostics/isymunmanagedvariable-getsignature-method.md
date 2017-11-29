---
title: "Метод ISymUnmanagedVariable::GetSignature"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedVariable.GetSignature
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedVariable::GetSignature
helpviewer_keywords:
- GetSignature method, ISymUnmanagedVariable interface [.NET Framework debugging]
- ISymUnmanagedVariable::GetSignature method [.NET Framework debugging]
ms.assetid: 78c1ba28-a410-4360-805c-23a95408964a
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1e29cd4a38e9abbe380b51b81fc2849b833d87e9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedvariablegetsignature-method"></a>Метод ISymUnmanagedVariable::GetSignature
Возвращает подпись переменной.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetSignature(  
    [in]  ULONG32  cSig,  
    [out] ULONG32  *pcSig,  
    [out, size_is(cSig),  
        length_is(*pcSig)] BYTE sig[]);  
```  
  
#### <a name="parameters"></a>Параметры  
 `cSig`  
 [in] Размер буфера, на который указывает `sig` параметра.  
  
 `pcSig`  
 [out] Указатель на `ULONG32` , получающий размер в символах, буфера, необходимый для подписи.  
  
 `sig`  
 [out] Буфер, содержит подписи.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>См. также  
 [ISymUnmanagedVariable-интерфейс](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
