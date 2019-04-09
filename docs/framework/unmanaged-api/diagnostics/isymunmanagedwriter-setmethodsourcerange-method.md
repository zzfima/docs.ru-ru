---
title: Метод ISymUnmanagedWriter::SetMethodSourceRange
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetMethodSourceRange
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetMethodSourceRange
helpviewer_keywords:
- SetMethodSourceRange method [.NET Framework debugging]
- ISymUnmanagedWriter::SetMethodSourceRange method [.NET Framework debugging]
ms.assetid: c698b86e-ace7-4b21-9549-f52d6a034959
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 734857428c205b6d806a4279213afb1193f914c8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59086173"
---
# <a name="isymunmanagedwritersetmethodsourcerange-method"></a>Метод ISymUnmanagedWriter::SetMethodSourceRange
Указывает истинные начало и конец метода в исходном файле. Используйте этот метод для задания длины метода независимо от точек следования, имеющихся в методе.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT SetMethodSourceRange(  
    [in] ISymUnmanagedDocumentWriter  *startDoc,  
    [in] ULONG32                      startLine,  
    [in] ULONG32                      startColumn,  
    [in] ISymUnmanagedDocumentWriter  *endDoc,  
    [in] ULONG32                      endLine,  
    [in] ULONG32                      endColumn);  
```  
  
## <a name="parameters"></a>Параметры  
 `startDoc`  
 [in] Указатель на документ, содержащий начальную позицию.  
  
 `startLine`  
 [in] Номер начальной строки.  
  
 `startColumn`  
 [in] Начальный столбец.  
  
 `endDoc`  
 [in] Указатель на документ, содержащий конечное положение.  
  
 `endLine`  
 [in] Номер конечной строки.  
  
 `endColumn`  
 [in] Номер конечного столбца.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок.** CorSym.idl CorSym.h  
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
