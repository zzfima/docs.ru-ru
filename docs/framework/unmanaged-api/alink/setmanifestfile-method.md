---
title: Метод SetManifestFile
ms.date: 03/30/2017
api_name:
- IALink3.SetManifestFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetManifestFile
helpviewer_keywords:
- SetManifestFile method
ms.assetid: 1b33de4c-19cb-4a36-a93f-8675b2a36d58
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8f8398c16b27836b772e8ac56ee1f7e8494f4be0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="setmanifestfile-method"></a>Метод SetManifestFile
Позволяет задать или сбросить файл манифеста, компоновщик использует при создании сборки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT SetManifestFile(  
    LPCWSTR pszFile  
) PURE;  
```  
  
#### <a name="parameters"></a>Параметры  
 `pszFile`  
  
 Имя файла манифеста, содержимое которого помещается в большой двоичный объект ресурсов Win32.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK, если метод выполнен успешно.  
  
## <a name="remarks"></a>Примечания  
 Это следует вызовите перед запросом Win32ResBlob. Значение `pszFile` параметр — имя файла манифеста, содержимое которого считывается и помещается в ресурсы Win32 с Идентификатором RT_MANIFEST. При вызове с помощью параметра NULL все считанные ранее манифесты очищается. Это позволяет сбросить состояние компоновщика для во время инициализации.  
  
## <a name="requirements"></a>Требования  
 Требуется aLink.h  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IALink3](../../../../docs/framework/unmanaged-api/alink/ialink3-interface.md)  
 [API ALink](../../../../docs/framework/unmanaged-api/alink/index.md)  
 [Интерфейс IALink](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [Al.exe (компоновщик сборок)](../../../../docs/framework/tools/al-exe-assembly-linker.md)
