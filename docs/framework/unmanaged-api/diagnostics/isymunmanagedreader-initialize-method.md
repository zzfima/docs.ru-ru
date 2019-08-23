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
ms.openlocfilehash: f2dceeb2f0b3aa9f3147157e77087dffbf2d5f85
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69939015"
---
# <a name="isymunmanagedreaderinitialize-method"></a>Метод ISymUnmanagedReader::Initialize
Инициализирует средство чтения символов с помощью интерфейса средства импорта метаданных, с которым будет связан этот модуль чтения, вместе с именем файла модуля.  
  
> [!NOTE]
> Этот метод может быть вызван только один раз и должен вызываться до любых других методов чтения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Initialize (  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *filename,  
    [in]  const WCHAR  *searchPath,  
    [in]  IStream      *pIStream);  
```  
  
## <a name="parameters"></a>Параметры  
 `importer`  
 окне Интерфейс средства импорта метаданных, с которым будет связан этот модуль чтения.  
  
 `filename`  
 окне Имя файла модуля. Вместо этого можно использовать `pIStream` параметр.  
  
 `searchPath`  
 окне Путь для поиска. Это необязательный параметр.  
  
 `pIStream`  
 окне Файловый поток, используемый в качестве альтернативы параметру filename.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если метод выполнен. в противном случае — E_FAIL или другой код ошибки.  
  
## <a name="remarks"></a>Примечания  
 Необходимо указать только один из `filename` `pIStream` параметров или, но не оба. Параметр `searchPath` является необязательным.  
  
## <a name="requirements"></a>Требования  
 **Заголовок.** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
