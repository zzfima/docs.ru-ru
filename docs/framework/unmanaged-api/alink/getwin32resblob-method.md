---
title: Метод GetWin32ResBlob
ms.date: 03/30/2017
api_name:
- IALink.GetWin32ResBlob
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetWin32ResBlob
helpviewer_keywords:
- GetWin32ResBlob method
ms.assetid: 36997e04-f9f6-4254-a041-6767ac6c51d9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b26f08548ac964fae2f4d64db50167add327eb2d
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777372"
---
# <a name="getwin32resblob-method"></a>Метод GetWin32ResBlob
Извлекает BLOB-объект ресурса Win32. Вызовите этот метод после установки параметров сборки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetWin32ResBlob(  
    mdAssembly    AssemblyID,  
    mdToken       FileToken,  
    BOOL          fDll,  
    LPCWSTR       pszIconFile,  
    const void**  ppResBlob,  
    DWORD*        pcbResBlob  
) PURE;  
```  
  
## <a name="parameters"></a>Параметры  
 `AssemblyID`  
 Идентификатор сборки.  
  
 `FileToken`  
 Токен файла, используемый для получения имени файла, используемого при создании ресурса версии Win32  
  
 `fDll`  
 Значение TRUE, если файл является библиотекой DLL, и false для EXE-файла.  
  
 `pszIconFile`  
 Необязательный значок для вставки в большой двоичный объект ресурса.  
  
 `ppResBlob`  
 Получает большой двоичный объект ресурса.  
  
 `pcbResBlob`  
 Получает размер большого двоичного объекта.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается с ошибкой, возвращает значение S_OK.  
  
## <a name="requirements"></a>Требования  
 Требуется ALink. h  
  
## <a name="see-also"></a>См. также

- [Интерфейс IALink](ialink-interface.md)
- [Интерфейс IALink2](ialink2-interface.md)
- [API ALink](index.md)
