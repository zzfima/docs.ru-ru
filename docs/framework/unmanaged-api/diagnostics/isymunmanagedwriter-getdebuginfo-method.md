---
title: "Метод ISymUnmanagedWriter::GetDebugInfo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f071bfe88397d6431fb50403c3969d82c5cfe8fc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwritergetdebuginfo-method"></a>Метод ISymUnmanagedWriter::GetDebugInfo
Возвращает информацию, необходимую для компилятора записать запись каталога отладки в заголовок переносимого исполняемого (PE) файла. Модуль записи символов заполнения всех полей, за исключением `TimeDateStamp` и `PointerToRawData`. (Компилятор отвечает за настройку этих полей соответствующим образом).  
  
 Компилятор должен вызвать этот метод, создавать большой двоичный объект, к PE-файла, задайте `PointerToRawData` в IMAGE_DEBUG_DIRECTORY пункты порожденную данных и запись IMAGE_DEBUG_DIRECTORY PE-файл. Компилятор также следует задать `TimeDateStamp` равным `TimeDateStamp` создаваемого PE-файла.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetDebugInfo(  
    [in, out] IMAGE_DEBUG_DIRECTORY *pIDD,  
    [in]  DWORD cData,  
    [out] DWORD *pcData,  
    [out, size_is(cData),  
        length_is(*pcData)] BYTE data[]);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pIDD`  
 [in, out] Указатель на IMAGE_DEBUG_DIRECTORY, заполняемой модуля записи символов.  
  
 `cData`  
 [in] Объект `DWORD` , содержащее размер данных отладки.  
  
 `pcData`  
 [out] Указатель на `DWORD` , получающий размер буфера, который должен содержать данные отладки.  
  
 `data`  
 [out] Указатель на буфер, достаточное для хранения данных для хранилища символов отладки.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
