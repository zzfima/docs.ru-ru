---
title: Метод ISymUnmanagedReader::Initialize
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.Initialize
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::Initialize
helpviewer_keywords:
- ISymUnmanagedReader::Initialize method [.NET Framework debugging]
- Initialize method, ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: 8f0dd2fe-7df7-464e-91f4-5518c586bb5f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ee68533e95deb4b6efaa9226c047599f233b3954
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54494760"
---
# <a name="isymunmanagedreaderinitialize-method"></a>Метод ISymUnmanagedReader::Initialize
Инициализирует средство чтения символов с интерфейсом средства импорта метаданных, что средство чтения будет сопоставлено, а также имя файла модуля.  
  
> [!NOTE]
>  Этот метод может вызываться только один раз и должен вызываться до всех остальных методов чтения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT Initialize (  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *filename,  
    [in]  const WCHAR  *searchPath,  
    [in]  IStream      *pIStream);  
```  
  
#### <a name="parameters"></a>Параметры  
 `importer`  
 [in] Интерфейс импорта метаданных, с которым будет связано данное средство чтения.  
  
 `filename`  
 [in] Имя файла модуля. Можно использовать `pIStream` параметра вместо этого.  
  
 `searchPath`  
 [in] Путь для поиска. Этот параметр является необязательным.  
  
 `pIStream`  
 [in] Файловый поток, используемый в качестве альтернативы в параметре filename.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.  
  
## <a name="remarks"></a>Примечания  
 Необходимо указать только один из `filename` или `pIStream` параметров, не оба. Параметр `searchPath` является необязательным.  
  
## <a name="requirements"></a>Требования  
 **Заголовок.** CorSym.idl CorSym.h  
  
## <a name="see-also"></a>См. также
- [Интерфейс ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
