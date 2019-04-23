---
title: Метод ISymENCUnmanagedMethod::GetLineFromOffset
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetLineFromOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetLineFromOffset
helpviewer_keywords:
- GetLineFromOffset method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetLineFromOffset method [.NET Framework debugging]
ms.assetid: cc09bad2-fb34-4d13-a521-6ec7b1a1d915
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3106c6680750826306cffb31e599ee2260bf4ad7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59136452"
---
# <a name="isymencunmanagedmethodgetlinefromoffset-method"></a>Метод ISymENCUnmanagedMethod::GetLineFromOffset
Получает сведения о строке, связанной со смещением. Если параметр смещения (`dwOffset`) не является точкой следования, этот метод возвращает сведения о строке, связанные с предыдущим смещением.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetLineFromOffset(  
     [in]  ULONG32   dwOffset,  
     [out] ULONG32*  pline,  
     [out] ULONG32*  pcolumn,  
     [out] ULONG32*  pendLine,  
     [out] ULONG32*  pendColumn,  
     [out] ULONG32*  pdwStartOffset);  
```  
  
## <a name="parameters"></a>Параметры  
 `dwOffset`  
 [in] Объект `ULONG32` , содержащий смещение.  
  
 `pline`  
 [out] Указатель на `ULONG32` , получающий строки.  
  
 `pcolumn`  
 [out] Указатель на `ULONG32` , получающий столбца.  
  
 `pendLine`  
 [out] Указатель на `ULONG32` , получающий конечную строку.  
  
 `pendColumn`  
 [out] Указатель на `ULONG32` , который получает конечный столбец.  
  
 `pdwStartOffset`  
 [out] Указатель на `ULONG32` , получающий точка связанные последовательности.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок.** CorSym.idl CorSym.h  
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymENCUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
