---
title: Интерфейс IMetaDataEmit
ms.date: 03/30/2017
api_name:
- IMetaDataEmit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit
helpviewer_keywords:
- IMetaDataEmit interface [.NET Framework metadata]
ms.assetid: 3b48fd47-7397-4e2c-8bec-8157aa08978c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 10942541b781d367820301588656b2f1fc2fd006
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59184422"
---
# <a name="imetadataemit-interface"></a>Интерфейс IMetaDataEmit
Предоставляет методы для создания, изменения и сохранить метаданные о сборке в текущей заданной области. Метаданные можно сохранять в памяти или на жестком диске.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод ApplyEditAndContinue](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-applyeditandcontinue-method.md)|Обновляет текущую область сборки с изменениями, внесенными в указанном `pImport`.|  
|[Метод DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md)|Создает определение настраиваемого атрибута с заданной подписью метаданных, должны быть присоединены к заданного объекта и получает маркер для этого определения настраиваемого атрибута.|  
|[Метод DefineEvent](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md)|Создает определение события с заданной подписью метаданных и получает маркер для определения событий.|  
|[Метод DefineField](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definefield-method.md)|Создает определение для поля с заданной подписью метаданных и получает маркер для этого определения поля.|  
|[Метод DefineImportMember](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimportmember-method.md)|Создает определение члена типа, определенных в модуле вне текущей области и получает маркер для этого определения ссылки.|  
|[Метод DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md)|Создает определение для ссылки на тип, который определен в модуле вне текущей области и получает маркер для этого определения ссылки.|  
|[Метод DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md)|Создает определение для ссылки на член модуля вне текущей области и получает маркер для этого определения ссылки.|  
|[Метод DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md)|Создает определение для метода с указанной сигнатурой и возвращает маркер для этого определения метода.|  
|[Метод DefineMethodImpl](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethodimpl-method.md)|Создает определение реализации метода, унаследованного от интерфейса и возвращает маркер для этого определения реализации метода.|  
|[Метод DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md)|Создает подпись метаданных для модуля с указанным именем.|  
|[Метод DefineNestedType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definenestedtype-method.md)|Создает подпись метаданных определения типа и возвращает `mdTypeDef` маркера для этого типа, кроме того, указывается, что определенный тип является членом типа, который ссылается `tdEncloser`.|  
|[Метод DefineParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md)|Создает определение параметра с указанной сигнатурой метода, который ссылается указанный токен и получает маркер для данного определения параметра.|  
|[Метод DefinePermissionSet](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepermissionset-method.md)|Создает определение набора разрешений с заданной подписью метаданных и получает маркер для этого определения набора разрешений.|  
|[Метод DefinePinvokeMap](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepinvokemap-method.md)|Задает функции PInvoke подписи метода, который ссылается указанный токен.|  
|[Метод DefineProperty](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md)|Создает определение свойства для указанного типа с заданным `get` и `set` метод доступа и получает маркер для этого определения свойства.|  
|[Метод DefineSecurityAttributeSet](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definesecurityattributeset-method.md)|Создает набор разрешений безопасности для прикрепления к объекту, который ссылается указанный токен.|  
|[Метод DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)|Создает определение типа для типа среды выполнения и получает маркер метаданных для этого определения типа.|  
|[Метод DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md)|Получает маркер метаданных для типа, который определен в другом модуле вне текущей области.|  
|[Метод DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md)|Получает маркер метаданных для заданной строки литерала.|  
|[Метод DeleteClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-deleteclasslayout-method.md)|Удаляет подпись метаданных структуры класса для типа, который ссылается указанный токен.|  
|[Метод DeleteFieldMarshal](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-deletefieldmarshal-method.md)|Уничтожает PInvoke, маршалинг подпись метаданных для объекта, который ссылается указанный токен.|  
|[Метод DeletePinvokeMap](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-deletepinvokemap-method.md)|Удаляет метаданные сопоставления PInvoke для объекта, который ссылается указанный токен.|  
|[Метод DeleteToken](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-deletetoken-method.md)|Удаляет указанный маркер из текущей области метаданных.|  
|[Метод GetSaveSize](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-getsavesize-method.md)|Получает приблизительный двоичный размер сборки в текущей области.|  
|[Метод GetTokenFromSig](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromsig-method.md)|Получает токен для заданной подписью метаданных.|  
|[Метод GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md)|Получает маркер метаданных для типа с заданной подписью метаданных.|  
|[Метод Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)|Добавляет указанный импортируемой области в список объединяемых областей.|  
|[Метод MergeEnd](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md)|Выполняет слияние в текущей области все области метаданных, определяемое один или несколько предыдущих вызовов `IMetaDataEmit::Merge`.|  
|[Метод Save](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-save-method.md)|Сохраняет все метаданные в текущей области в файл по указанному адресу.|  
|[Метод SaveToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetomemory-method.md)|Сохраняет все метаданные в текущей области к указанной области памяти.|  
|[Метод SaveToStream](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetostream-method.md)|Сохраняет все метаданные в текущей области в указанном `IStream`.|  
|[Метод SetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setclasslayout-method.md)|Задает или обновляет подпись структуры класса для типа, определенного во время предыдущего вызова `IMetaDataEmit::DefineTypeDef`.|  
|[Метод SetCustomAttributeValue](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setcustomattributevalue-method.md)|Задает или обновляет значение настраиваемого атрибута определен с помощью предыдущего вызова `IMetaDataEmit::DefineCustomAttribute`.|  
|[Метод SetEventProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-seteventprops-method.md)|Задает или обновляет указанный компонент события, определенного с помощью предыдущего вызова `IMetaDataEmit::DefineEvent`.|  
|[Метод SetFieldMarshal](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setfieldmarshal-method.md)|Задает сведения о маршалинге для параметра поля, возвращаемого значения метода или метода ссылается указанный токен PInvoke.|  
|[Метод SetFieldProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setfieldprops-method.md)|Задает или обновляет значение по умолчанию для поля, который ссылается токен указанного поля.|  
|[Метод SetFieldRVA](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setfieldrva-method.md)|Задает значение глобальной переменной для относительного виртуального адреса поля, который ссылается указанный токен.|  
|[Метод SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md)|Задает метод, который ссылается заданный `IUnknown` указатель в виде обратного вызова уведомления для повторного сопоставления маркера.|  
|[Метод SetMethodImplFlags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md)|Задает или обновляет подпись метаданных реализации унаследованного метода, который ссылается указанный токен.|  
|[Метод SetMethodProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodprops-method.md)|Задает или обновляет функцию, хранимую в указанного относительного виртуального адреса, определенные с помощью предыдущего вызова метода `IMetaDataEmit::DefineMethod`.|  
|[Метод SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md)|Обновляет ссылки на модуль, определенные с помощью предыдущего вызова `IMetaDataEmit::DefineModuleRef`.|  
|[Метод SetParamProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md)|Задает или изменяет функции параметра метода, который определен с помощью предыдущего вызова `IMetaDataEmit::DefineParam`.|  
|[Метод SetParent](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparent-method.md)|Определяет, что указанный член, в соответствии с предыдущего вызова `IMetaDataEmit::DefineMemberRef`, является членом указанного типа, в соответствии с определением предыдущего вызова `IMetaDataEmit::DefineTypeDef`.|  
|[Метод SetPermissionSetProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setpermissionsetprops-method.md)|Задает или обновляет функции сигнатуры метаданных набора разрешений, определенные с помощью предыдущего вызова `IMetaDataEmit::DefinePermissionSet`.|  
|[Метод SetPinvokeMap](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setpinvokemap-method.md)|Задает или изменяет функции сигнатуры метода PInvoke, в соответствии с определением предыдущего вызова `IMetaDataEmit::DefinePinvokeMap`.|  
|[Метод SetPropertyProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setpropertyprops-method.md)|Задает хранится в метаданных для свойства, определенные с помощью предыдущего вызова функции `IMetaDataEmit::DefineProperty`.|  
|[Метод SetRVA](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md)|Задает относительный виртуальный адрес указанного метода.|  
|[Метод SetTypeDefProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-settypedefprops-method.md)|Задает тип, определенный с помощью предыдущего вызова функции `IMetaDataEmit::DefineTypeDef`.|  
|[Метод TranslateSigWithScope](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-translatesigwithscope-method.md)|Импортирует сборки в текущей области и возвращает новую подпись метаданных для объединенных области.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Используется как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [Интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
