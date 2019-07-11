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
ms.openlocfilehash: bdc1ef6490f250ebe93b0482adf244adfc0ffd56
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741783"
---
# <a name="getwin32resblob-method"></a>Метод GetWin32ResBlob
Извлекает большой двоичный объект ресурса Win32. Этот метод вызывается после задания параметров сборки.  
  
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
 Файл токен, используемый для извлечения имени файла для использования при создании ресурс версии Win32  
  
 `fDll`  
 Значение TRUE, если файл является библиотекой DLL, false для EXE-файла.  
  
 `pszIconFile`  
 Необязательный значок для вставки в большой двоичный объект ресурса.  
  
 `ppResBlob`  
 Получает большой двоичный объект ресурса.  
  
 `pcbResBlob`  
 Получает размер большого двоичного объекта.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает S_OK, если метод выполнен успешно.  
  
## <a name="requirements"></a>Требования  
 Требуется alink.h  
  
## <a name="see-also"></a>См. также

- [Интерфейс IALink](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [Интерфейс IALink2](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [API ALink](../../../../docs/framework/unmanaged-api/alink/index.md)
