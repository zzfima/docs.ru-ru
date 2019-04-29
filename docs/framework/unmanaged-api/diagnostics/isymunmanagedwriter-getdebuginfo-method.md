---
title: Метод ISymUnmanagedWriter::GetDebugInfo
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.GetDebugInfo
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::GetDebugInfo
helpviewer_keywords:
- ISymUnmanagedWriter::GetDebugInfo method [.NET Framework debugging]
- GetDebugInfo method [.NET Framework debugging]
ms.assetid: dd31c210-6829-45eb-927e-cc53932638b7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 41d96c6d2024dbc3cab669f2dba2f99faef89f4b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61701298"
---
# <a name="isymunmanagedwritergetdebuginfo-method"></a>Метод ISymUnmanagedWriter::GetDebugInfo
Возвращает информацию, необходимую для компилятора, чтобы написать запись каталога отладки в заголовок переносимого исполняемого (PE) файла. Модуль записи символов заполнения всех полей, за исключением `TimeDateStamp` и `PointerToRawData`. (Компилятор отвечает за правильную настройку этих полей.)  
  
 Компилятор должен вызывать этот метод, порождаемого большой двоичный объект данных к PE-файлу, задайте `PointerToRawData` в IMAGE_DEBUG_DIRECTORY пункты порожденную данных и запись IMAGE_DEBUG_DIRECTORY PE-файл. Компилятор также следует задать `TimeDateStamp` равным `TimeDateStamp` создаваемого PE-файла.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetDebugInfo(  
    [in, out] IMAGE_DEBUG_DIRECTORY *pIDD,  
    [in]  DWORD cData,  
    [out] DWORD *pcData,  
    [out, size_is(cData),  
        length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a>Параметры  
 `pIDD`  
 [in, out] Указатель на IMAGE_DEBUG_DIRECTORY, заполняемой интерфейс записи символов.  
  
 `cData`  
 [in] Объект `DWORD` , содержащий размер данных отладки.  
  
 `pcData`  
 [out] Указатель на `DWORD` , принимает размер буфера, требуемого для хранения данных отладки.  
  
 `data`  
 [out] Указатель на буфер, достаточно велик для хранения данных в хранилище символов отладки.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок.** CorSym.idl CorSym.h  
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
