---
title: "Метод ISymUnmanagedWriter::DefineLocalVariable"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.DefineLocalVariable
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::DefineLocalVariable
helpviewer_keywords:
- ISymUnmanagedWriter::DefineLocalVariable method [.NET Framework debugging]
- DefineLocalVariable method [.NET Framework debugging]
ms.assetid: 6fab8a58-3883-490f-8b27-64042c90f104
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e454aa2c2dd8ceb8f8dbbc03bdd1e70e8a800de2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedwriterdefinelocalvariable-method"></a>Метод ISymUnmanagedWriter::DefineLocalVariable
Определяет одну переменную в текущей лексической области видимости. Этот метод может вызываться несколько раз для переменной с тем же именем, имеющей несколько корневых в пределах области. В этом случае, однако значения `startOffset` и `endOffset` параметров не должны перекрываться.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT DefineLocalVariable(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      cSig,  
    [in, size_is(cSig)] unsigned char signature[],  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3,  
    [in] ULONG32      startOffset,  
    [in] ULONG32      endOffset);  
```  
  
#### <a name="parameters"></a>Параметры  
 `name`  
 [in] Указатель на `WCHAR` , определяющий имя локальной переменной.  
  
 `attributes`  
 [in] Атрибуты локальной переменной.  
  
 `cSig`  
 [in] Объект `ULONG32` указывает размер в байтах для `signature` буфера.  
  
 `signature`  
 [in] Подпись локальной переменной.  
  
 `addrKind`  
 [in] Тип адреса.  
  
 `addr1`  
 [in] Первый адрес для спецификации параметра.  
  
 `addr2`  
 [in] Второй адрес для спецификации параметра.  
  
 `addr3`  
 [in] Третий адрес для спецификации параметра.  
  
 `startOffset`  
 [in] Начальное смещение для переменной. Этот параметр является необязательным. Если задано значение 0, этот параметр пропускается и переменная определяется для всей области. Если ненулевое значение, переменная находится в границах смещений текущей области.  
  
 `endOffset`  
 [in] Конечное смещение для переменной. Этот параметр является необязательным. Если задано значение 0, этот параметр пропускается и переменная определяется для всей области. Если ненулевое значение, переменная находится в границах смещений текущей области.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>См. также  
 [ISymUnmanagedWriter-интерфейс](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [Метод DefineGlobalVariable](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineglobalvariable-method.md)  
 [Метод DefineLocalVariable2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-definelocalvariable2-method.md)
