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
ms.openlocfilehash: b293c30060107d18c6b609efc82c4128a73cc1c7
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787209"
---
# <a name="setmanifestfile-method"></a>Метод SetManifestFile
Позволяет указать или сбросить файл манифеста, используемый компоновщиком при создании сборки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetManifestFile(  
    LPCWSTR pszFile  
) PURE;  
```  
  
## <a name="parameters"></a>Параметры  
 `pszFile`  
  
 Имя файла манифеста, содержимое которого помещается в большой двоичный объект Win32 Resources.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается с ошибкой, возвращает значение S_OK.  
  
## <a name="remarks"></a>Примечания  
 Вызовите этот метод, прежде чем запрашивать Win32ResBlob. Значение `pszFile` параметра — это имя файла манифеста, содержимое которого считывается и помещается в ресурсы Win32 с идентификатором RT_MANIFEST. При вызове с помощью параметра NULL все ранее прочитанные манифесты очищаются. Это позволяет сбросить состояние компоновщика до значения времени инициализации.  
  
## <a name="requirements"></a>Требования  
 Требуется aLink. h  
  
## <a name="see-also"></a>См. также

- [Интерфейс IALink3](ialink3-interface.md)
- [API ALink](index.md)
- [Интерфейс IALink](ialink-interface.md)
- [Al.exe (компоновщик сборок)](../../tools/al-exe-assembly-linker.md)
