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
ms.openlocfilehash: ac76ef58badcc8e443279415b7239c0b6017af3e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="isymunmanagedwriterinitialize2-method"></a>Метод ISymUnmanagedWriter::Initialize2
Задает интерфейс включения метаданных, с которым будет связано данное средство записи и задает имя выходного файла, в который записываются символы отладки. Этот метод также позволяет задать конечное расположение файла базы данных (PDB) программы.  
  
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
 [in] Если указан, модуль записи символов выдает символы в данной <xref:System.Runtime.InteropServices.ComTypes.IStream> , а не файл, указанный в `filename` параметра. Параметр `pIStream` является необязательным.  
  
 `fFullBuild`  
 [in] `true` Если это полное перестроение; `false` Если это добавочная компиляция.  
  
 `finalfilename`  
 [in] Указатель на `WCHAR` в конечное расположение PDB-файла, то есть строки пути.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [Метод Initialize](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize-method.md)
