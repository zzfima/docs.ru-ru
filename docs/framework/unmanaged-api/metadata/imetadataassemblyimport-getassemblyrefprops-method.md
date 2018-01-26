---
title: "Метод IMetaDataAssemblyImport::GetAssemblyRefProps"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport.GetAssemblyRefProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport::GetAssemblyRefProps
helpviewer_keywords:
- IMetaDataAssemblyImport::GetAssemblyRefProps method [.NET Framework metadata]
- GetAssemblyRefProps method [.NET Framework metadata]
ms.assetid: 5c6b7fb4-cbca-4479-b650-ab9a99732ea0
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 76ae1d81db314530ab33a42cb99824da1745dff0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyimportgetassemblyrefprops-method"></a>Метод IMetaDataAssemblyImport::GetAssemblyRefProps
Получает набор свойств для ссылки на сборку с заданной подписью метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetAssemblyRefProps (  
    [in]  mdAssemblyRef        mdar,   
    [out] const void          **ppbPublicKeyOrToken,   
    [out] ULONG                *pcbPublicKeyOrToken,   
    [out] LPWSTR               szName,   
    [in]  ULONG                cchName,   
    [out] ULONG                *pchName,   
    [out] ASSEMBLYMETADATA     *pMetaData,   
    [out] const void           **ppbHashValue,   
    [out] ULONG                *pcbHashValue,   
    [out] DWORD                *pdwAssemblyRefFlags  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `mdar`  
 [in] `mdAssemblyRef` Токен метаданных, представляющий ссылку на сборку, для которого нужно получить свойства.  
  
 `ppbPublicKeyOrToken`  
 [out] Указатель на открытый ключ или маркер метаданных.  
  
 `pcbPublicKeyOrToken`  
 [out] Число байтов в возвращаемый открытый ключ или маркер.  
  
 `szName`  
 [out] Простое имя сборки.  
  
 `cchName`  
 [in] Размер в расширенных символов из `szName`.  
  
 `pchName`  
 [out] Указатель на число расширенных символов, фактически извлеченных в `szName`.  
  
 `pMetaData`  
 [out] Указатель на структуру ASSEMBLYMETADATA, которая содержит метаданные сборки.  
  
 `ppbHashValue`  
 [out] Указатель с хэш-значением. Это хэш, с помощью алгоритма SHA-1, из `PublicKey` свойства сборки, на которую выполняется ссылка, если флаг arfFullOriginator [AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) набор перечисления.  
  
 `pcbHashValue`  
 [out] Число расширенных символов в возвращенное хэш-значение.  
  
 `pdwAssemblyRefFlags`  
 [out] Указатель флаги, описывающие метаданные, применяемые к сборке. Значение флагов представляет собой сочетание одного или нескольких [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) значения.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает значение S_OK, если он выполняется успешно. в противном случае он возвращает один из кодов ошибок, определенных в файле заголовка Winerror.h.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** используется как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
