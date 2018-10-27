---
title: Метод ISymUnmanagedBinder2::GetReaderForFile2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder2.GetReaderForFile2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder2::GetReaderForFile2
helpviewer_keywords:
- ISymUnmanagedBinder2::GetReaderForFile2 method [.NET Framework debugging]
- GetReaderForFile2 method [.NET Framework debugging]
ms.assetid: dd92dcaf-403c-464d-a254-21594985dddd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e133333d735ca53d194bbb535710bc62bde6bb0e
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50188460"
---
# <a name="isymunmanagedbinder2getreaderforfile2-method"></a>Метод ISymUnmanagedBinder2::GetReaderForFile2
Данный интерфейс метаданных и имя файла, возвращает правильный [ISymUnmanagedReader](isymunmanagedreader-interface.md) интерфейс, который будет считывать символы отладки, связанные с модулем.  
  
 Этот метод предоставляет расширенный поиск файла базы данных (PDB) программы, чем [ISymUnmanagedBinder::GetReaderForFile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) метод.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetReaderForFile2(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [in]  ULONG32      searchPolicy,  
    [out,retval] ISymUnmanagedReader  **pRetVal);  
```  
  
## <a name="parameters"></a>Параметры  
 `importer`  
 [in] Указатель на интерфейс импорта метаданных.  
  
 `fileName`  
 [in] Указатель на имя файла.  
  
 `searchPath`  
 [in] Указатель на пути поиска.  
  
 `searchPolicy`  
 [in] Значение [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) перечисления, которое указывает политику, используемую при выполнении поиска для средства чтения символов.  
  
 `pRetVal`  
 [out] Указатель, который имеет значение равное возвращаемому [ISymUnmanagedReader](isymunmanagedreader-interface.md) интерфейс.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** CorSym.idl, CorSym.h  
  
## <a name="remarks"></a>Примечания  
 Эта версия метода можно найти PDB-файл в областях, отличных от рядом с модуля. Поиск политики можно управлять путем объединения [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md). Например `AllowReferencePathAccess | AllowSymbolServerAccess` производит поиск PDB рядом с исполняемым файлом и с сервера, но не отправки запроса в реестр или использовать путь в исполняемом файле. Если `searchPath` параметр указан, всегда найдет эти каталоги.  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ISymUnmanagedBinder2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)  
 [Метод GetReaderForFile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)
