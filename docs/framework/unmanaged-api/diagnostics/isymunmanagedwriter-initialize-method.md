---
title: Метод ISymUnmanagedWriter::Initialize
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Initialize
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Initialize
helpviewer_keywords:
- ISymUnmanagedWriter::Initialize method [.NET Framework debugging]
- Initialize method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: e0ebd793-3764-4df0-8f12-0e95f60b9eae
topic_type:
- apiref
ms.openlocfilehash: 6e9ab623d5fe9fcfda2305df078e988a561afdc5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427974"
---
# <a name="isymunmanagedwriterinitialize-method"></a>Метод ISymUnmanagedWriter::Initialize
Задает интерфейс передатчика метаданных, с которым будет связан этот модуль записи, и задает имя выходного файла, в который будут записываться отладочные символы.  
  
 Этот метод может быть вызван только один раз и должен вызываться перед любым другим методом записи. Некоторым модулям записи может потребоваться имя файла. Однако всегда можно передать имя файла этому методу без какого-либо негативного воздействия на модули записи, которые не используют имя файла.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Initialize(  
    [in] IUnknown     *emitter,  
    [in] const WCHAR  *filename,  
    [in] IStream      *pIStream,  
    [in] BOOL         fFullBuild);  
```  
  
## <a name="parameters"></a>Параметры  
 `emitter`  
 окне Указатель на интерфейс передатчика метаданных.  
  
 `filename`  
 окне Имя файла, в который записываются отладочные символы. Если имя файла задано для модуля записи, который не использует имена файлов, этот параметр пропускается.  
  
 `pIStream`  
 окне Если этот параметр указан, модуль записи символов выдает символы в заданный <xref:System.Runtime.InteropServices.ComTypes.IStream>, а не в файл, указанный в `filename`. Параметр `pIStream` является необязательным.  
  
 `fFullBuild`  
 [in] `true`, если это полная перестроение; `false`, если это инкрементная компиляция.  
  
## <a name="return-value"></a>Возвращаемое значение  
 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [Метод Initialize2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize2-method.md)
