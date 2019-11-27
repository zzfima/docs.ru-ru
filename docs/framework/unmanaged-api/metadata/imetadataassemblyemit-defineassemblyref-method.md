---
title: Метод IMetaDataAssemblyEmit::DefineAssemblyRef
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineAssemblyRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineAssemblyRef
helpviewer_keywords:
- DefineAssemblyRef method [.NET Framework metadata]
- IMetaDataAssemblyEmit::DefineAssemblyRef method [.NET Framework metadata]
ms.assetid: 0b284b18-0084-4b3a-912a-5ebe9f29c88b
topic_type:
- apiref
ms.openlocfilehash: c88b7a401a19b1bd0e02edab7ef7bbee1372199e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432078"
---
# <a name="imetadataassemblyemitdefineassemblyref-method"></a>Метод IMetaDataAssemblyEmit::DefineAssemblyRef
Создает структуру `AssemblyRef`, содержащую метаданные для сборки, на которую ссылается данная сборка, и возвращает связанный токен метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT DefineAssemblyRef (  
    [in]  void                *pbPublicKeyOrToken,  
    [in]  ULONG               cbPublicKeyOrToken,  
    [in]  LPCWSTR             szName,  
    [in]  ASSEMBLYMETADATA    pMetaData,  
    [in]  void                *pbHashValue,  
    [in]  ULONG               cbHashValue,  
    [in]  DWORD               dwAssemblyRefFlags,  
    [out] mdAssemblyRef       *pmdar  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pbPublicKeyOrToken`  
 окне Открытый ключ издателя сборки, на которую указывает ссылка. Вспомогательную функцию [StrongNameTokenFromAssembly](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassembly-function.md) можно использовать, чтобы получить хэш открытого ключа для передачи в качестве этого параметра.  
  
 `cbPublicKeyOrToken`  
 окне Размер в байтах `pbPublicKeyOrToken`.  
  
 `szName`  
 окне Понятное для человека текстовое имя сборки. Это значение не должно превышать 1024 символов.  
  
 `pMetaData`  
 окне Экземпляр ASSEMBLYMETADATA, содержащий сведения о версии, платформе и языковой стандарте сборки, на которую указывает ссылка.  
  
 `pbHashValue`  
 окне Хэш-данные, связанные с упоминаемой сборкой. Необязательно.  
  
 `cbHashValue`  
 окне Размер в байтах `pbHashValue`.  
  
 `dwAssemblyRefFlags`  
 окне Побитовое сочетание значений [корассемблифлагс](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) , влияющих на поведение подсистемы выполнения.  
  
 `pmdar`  
 заполняет Указатель на возвращаемый маркер `AssemblyRef` метаданных.  
  
## <a name="remarks"></a>Примечания  
 Для каждой сборки, на которую ссылается эта сборка, необходимо определить одну `AssemblyRef` структуру метаданных.  
  
 Во время выполнения сведения о сборке, на которую указывает ссылка, передаются распознавателю сборок с указанием, что они представляют "как встроенные" сведения. Затем сопоставитель сборок применяет политику.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
