---
title: Метод IMetaDataAssemblyEmit::SetAssemblyProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetAssemblyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetAssemblyProps
helpviewer_keywords:
- SetAssemblyProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetAssemblyProps method [.NET Framework metadata]
ms.assetid: 91b633d7-9e75-43c3-a8d2-2144984e5f9e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3361212f9a7f7ff0739e8544419a2b67abc8f457
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59214654"
---
# <a name="imetadataassemblyemitsetassemblyprops-method"></a>Метод IMetaDataAssemblyEmit::SetAssemblyProps
Изменяет указанную структуру метаданных `Assembly`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT SetAssemblyProps (  
    [in] mdAssembly               pma,  
    [in] const void               *pbPublicKey,  
    [in] ULONG                    cbPublicKey,  
    [in] ULONG                    ulHashAlgId,  
    [in] LPCWSTR                  szName,  
    [in] const ASSEMBLYMETADATA   *pMetaData,  
    [in] DWORD                    dwAssemblyFlags  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pma`  
 [in] Токен метаданных, указывающее `Assembly` изменение структуры метаданных.  
  
 `pbPublicKey`  
 [in] Указатель на открытый ключ издателя сборки.  
  
 `cbPublicKey`  
 [in] Размер в байтах `pbPublicKey`.  
  
 `ulHashAlgId`  
 [in] Идентификатор хэш-алгоритм, используемый для хэширования файлов сборки.  
  
 `szName`  
 [in] Понятное текстовое имя сборки.  
  
 `pMetaData`  
 [in] Указатель на ASSEMBLYMETADATA, содержащий сведения о версии, платформы и языка для сборки.  
  
 `dwAssemblyFlags`  
 [in] Побитовое сочетание [AssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md) значения, которые определяют различные атрибуты сборки.  
  
## <a name="remarks"></a>Примечания  
 Чтобы создать `Assembly` структура метаданных, используйте [IMetaDataAssemblyEmit::DefineAssembly](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassembly-method.md) метод.  
  
## <a name="requirements"></a>Требования  
 **Платформа:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Используется как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
