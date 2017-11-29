---
title: "Метод ISymUnmanagedReader::Initialize"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.Initialize
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::Initialize
helpviewer_keywords:
- ISymUnmanagedReader::Initialize method [.NET Framework debugging]
- Initialize method, ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: 8f0dd2fe-7df7-464e-91f4-5518c586bb5f
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5917fbe3cebe9b1e9ab91d113aee2461f414c14d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedreaderinitialize-method"></a>Метод ISymUnmanagedReader::Initialize
Инициализирует средства чтения символов, при этом интерфейс импорта метаданных, данное средство чтения связанного с, а также имя файла модуля.  
  
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
 [in] Файловый поток, используемый вместо параметра filename.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.  
  
## <a name="remarks"></a>Примечания  
 Необходимо указать только один из `filename` или `pIStream` параметров, не оба. Параметр `searchPath` является необязательным.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>См. также  
 [ISymUnmanagedReader-интерфейс](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
