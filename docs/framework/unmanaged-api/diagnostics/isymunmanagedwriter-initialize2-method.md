---
title: Метод ISymUnmanagedWriter::Initialize2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Initialize2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Initialize2
helpviewer_keywords:
- ISymUnmanagedWriter::Initialize2 method [.NET Framework debugging]
- Initialize2 method [.NET Framework debugging]
ms.assetid: 93de56b6-4ae8-4cca-acdc-25a434623509
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f65262a9b9850d93e934a77f154bb625a55e1e82
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54514248"
---
# <a name="isymunmanagedwriterinitialize2-method"></a>Метод ISymUnmanagedWriter::Initialize2
Задает интерфейс включения метаданных, с которым будет связан этот модуль записи и задает имя выходного файла, в который записываются символы отладки. Этот метод также позволяет задать конечное расположение файла базы данных (PDB) программы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT Initialize2(  
    [in] IUnknown     *emitter,  
    [in] const WCHAR  *tempfilename,  
    [in] IStream      *pIStream,  
    [in] BOOL         fFullBuild,  
    [in] const WCHAR  *finalfilename);  
```  
  
#### <a name="parameters"></a>Параметры  
 `emitter`  
 [in] Указатель на интерфейс включения метаданных.  
  
 `tempfilename`  
 [in] Указатель на `WCHAR` , содержащий имя файла, в который записываются символы отладки. Если имя файла задано для модуля записи, который не использует имена файлов, этот параметр пропускается.  
  
 `pIStream`  
 [in] Если указан, модуль записи символов выдает символы в заданной <xref:System.Runtime.InteropServices.ComTypes.IStream> , а не файл, указанный в `filename` параметра. Параметр `pIStream` является необязательным.  
  
 `fFullBuild`  
 [in] `true` Если это полное перестроение; `false` Если это добавочная компиляция.  
  
 `finalfilename`  
 [in] Указатель на `WCHAR` то есть строка пути в конечное расположение PDB-файл.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок.** CorSym.idl CorSym.h  
  
## <a name="see-also"></a>См. также
- [Интерфейс ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [Метод Initialize](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize-method.md)
