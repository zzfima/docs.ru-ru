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
ms.openlocfilehash: 8737885015055994bff3f6066bccb551f19f74f4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777317"
---
# <a name="isymunmanagedwritergetdebuginfo-method"></a>Метод ISymUnmanagedWriter::GetDebugInfo
Возвращает информацию, необходимую для компилятора, чтобы написать запись каталога отладки в заголовок переносимого исполняемого (PE) файла. Модуль записи символов заполнения всех полей, за исключением `TimeDateStamp` и `PointerToRawData`. (Компилятор отвечает за правильную настройку этих полей.)  
  
 Компилятор должен вызывать этот метод, порождаемого большой двоичный объект данных к PE-файлу, задайте `PointerToRawData` в IMAGE_DEBUG_DIRECTORY пункты порожденную данных и запись IMAGE_DEBUG_DIRECTORY PE-файл. Компилятор также следует задать `TimeDateStamp` равным `TimeDateStamp` создаваемого PE-файла.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
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
