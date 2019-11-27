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
ms.openlocfilehash: b4ae599a0e5cdb604fd9a610728671b39c67af31
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440895"
---
# <a name="imetadataemit-interface"></a>Интерфейс IMetaDataEmit
Предоставляет методы для создания, изменения и сохранения метаданных сборки в области, определенной в данный момент. Метаданные могут храниться в памяти или сохраняться на диск.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод ApplyEditAndContinue](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-applyeditandcontinue-method.md)|Обновляет текущую область сборки изменениями, внесенными в указанный `pImport`.|  
|[Метод DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md)|Создает определение для настраиваемого атрибута с указанной подписью метаданных, присоединяемого к указанному объекту и получает маркер для этого определения настраиваемого атрибута.|  
|[Метод DefineEvent](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md)|Создает определение для события с указанной сигнатурой метаданных и получает маркер для этого определения события.|  
|[Метод DefineField](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definefield-method.md)|Создает определение для поля с указанной сигнатурой метаданных и получает маркер для этого определения поля.|  
|[Метод DefineImportMember](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimportmember-method.md)|Создает определение для члена типа, который определен в модуле за пределами текущей области, и получает маркер для этого определения ссылки.|  
|[Метод DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md)|Создает определение для ссылки на тип, который определен в модуле за пределами текущей области, и получает маркер для этого эталонного определения.|  
|[Метод DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md)|Создает определение для ссылки на член модуля за пределами текущей области и получает маркер для этого эталонного определения.|  
|[Метод DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md)|Создает определение для метода с указанной сигнатурой и возвращает маркер в это определение метода.|  
|[Метод DefineMethodImpl](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethodimpl-method.md)|Создает определение для реализации метода, унаследованного от интерфейса, и возвращает маркер для этого определения реализации метода.|  
|[Метод DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md)|Создает подпись метаданных для модуля с указанным именем.|  
|[Метод DefineNestedType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definenestedtype-method.md)|Создает сигнатуру метаданных определения типа и возвращает маркер `mdTypeDef` для этого типа, кроме указания того, что определенный тип является членом типа, на который ссылается `tdEncloser`.|  
|[Метод DefineParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md)|Создает определение параметра с указанной сигнатурой для метода, на который ссылается указанный токен, и получает маркер для этого определения параметра.|  
|[Метод DefinePermissionSet](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepermissionset-method.md)|Создает определение для набора разрешений с указанной сигнатурой метаданных и получает маркер для этого определения набора разрешений.|  
|[Метод DefinePinvokeMap](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepinvokemap-method.md)|Задает функции сигнатуры PInvoke метода, на который ссылается указанный токен.|  
|[Метод DefineProperty](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md)|Создает определение свойства для указанного типа с указанными методами доступа `get` и `set` и получает маркер для этого определения свойства.|  
|[Метод DefineSecurityAttributeSet](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definesecurityattributeset-method.md)|Создает набор разрешений безопасности для присоединения к объекту, на который ссылается указанный токен.|  
|[Метод DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)|Создает определение типа для типа среды CLR и получает маркер метаданных для этого определения типа.|  
|[Метод DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md)|Возвращает токен метаданных для типа, определенного в другом модуле за пределами текущей области.|  
|[Метод DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md)|Возвращает токен метаданных для указанной литеральной строки.|  
|[Метод DeleteClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-deleteclasslayout-method.md)|Уничтожает сигнатуру метаданных макета класса для типа, на который ссылается указанный токен.|  
|[Метод DeleteFieldMarshal](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-deletefieldmarshal-method.md)|Уничтожает сигнатуру метаданных упаковки PInvoke для объекта, на который ссылается указанный токен.|  
|[Метод DeletePinvokeMap](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-deletepinvokemap-method.md)|Уничтожает метаданные сопоставления PInvoke для объекта, на который ссылается указанный токен.|  
|[Метод DeleteToken](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-deletetoken-method.md)|Удаляет указанный токен из текущей области метаданных.|  
|[Метод GetSaveSize](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-getsavesize-method.md)|Возвращает приблизительный двоичный размер сборки в текущей области.|  
|[Метод GetTokenFromSig](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromsig-method.md)|Возвращает токен для указанной сигнатуры метаданных.|  
|[Метод GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md)|Возвращает токен метаданных для типа с указанной сигнатурой метаданных.|  
|[Метод Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)|Добавляет указанную импортированную область в список объединяемых областей.|  
|[Метод MergeEnd](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md)|Выполняет слияние в текущую область всех областей метаданных, указанных одним или несколькими ранними вызовами `IMetaDataEmit::Merge`.|  
|[Метод Save](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-save-method.md)|Сохраняет все метаданные в текущей области в файле по указанному адресу.|  
|[Метод SaveToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetomemory-method.md)|Сохраняет все метаданные в текущей области в указанную область памяти.|  
|[Метод SaveToStream](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetostream-method.md)|Сохраняет все метаданные в текущей области в указанном `IStream`.|  
|[Метод SetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setclasslayout-method.md)|Задает или обновляет сигнатуру макета класса для типа, определенного в предыдущем вызове метода `IMetaDataEmit::DefineTypeDef`.|  
|[Метод SetCustomAttributeValue](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setcustomattributevalue-method.md)|Задает или обновляет значение настраиваемого атрибута, определенного при предыдущем вызове метода `IMetaDataEmit::DefineCustomAttribute`.|  
|[Метод SetEventProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-seteventprops-method.md)|Задает или обновляет указанную функцию события, определенного при предыдущем вызове метода `IMetaDataEmit::DefineEvent`.|  
|[Метод SetFieldMarshal](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setfieldmarshal-method.md)|Задает сведения о маршалировании PInvoke для поля, возвращаемого метода или параметра метода, на который ссылается указанный токен.|  
|[Метод SetFieldProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setfieldprops-method.md)|Задает или обновляет значение по умолчанию для поля, на которое ссылается заданный токен поля.|  
|[Метод SetFieldRVA](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setfieldrva-method.md)|Задает значение глобальной переменной для относительного виртуального адреса поля, на которое ссылается указанный токен.|  
|[Метод SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md)|Задает метод, на который ссылается указанный указатель `IUnknown` в качестве обратного вызова уведомления для повторного сопоставления токенов.|  
|[Метод SetMethodImplFlags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md)|Задает или обновляет сигнатуру метаданных реализации унаследованного метода, на которую ссылается указанный токен.|  
|[Метод SetMethodProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodprops-method.md)|Задает или обновляет компонент, хранящийся по указанному относительному виртуальному адресу метода, определенного в предыдущем вызове функции `IMetaDataEmit::DefineMethod`.|  
|[Метод SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md)|Обновляет ссылки на модуль, определенный при предыдущем вызове метода `IMetaDataEmit::DefineModuleRef`.|  
|[Метод SetParamProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md)|Задает или изменяет функции параметра метода, который был определен при предыдущем вызове `IMetaDataEmit::DefineParam`.|  
|[Метод SetParent](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparent-method.md)|Устанавливает, что указанный элемент, определенный в предыдущем вызове `IMetaDataEmit::DefineMemberRef`, является членом указанного типа, как определено в предыдущем вызове метода `IMetaDataEmit::DefineTypeDef`.|  
|[Метод SetPermissionSetProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setpermissionsetprops-method.md)|Задает или обновляет функции сигнатуры метаданных набора разрешений, определенного при предыдущем вызове метода `IMetaDataEmit::DefinePermissionSet`.|  
|[Метод SetPinvokeMap](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setpinvokemap-method.md)|Задает или изменяет функции сигнатуры PInvoke метода, как определено в предыдущем вызове `IMetaDataEmit::DefinePinvokeMap`.|  
|[Метод SetPropertyProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setpropertyprops-method.md)|Задает функции, хранимые в метаданных для свойства, определенного при предыдущем вызове метода `IMetaDataEmit::DefineProperty`.|  
|[Метод SetRVA](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md)|Задает относительный виртуальный адрес указанного метода.|  
|[Метод SetTypeDefProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-settypedefprops-method.md)|Задает функции типа, определенного при предыдущем вызове метода `IMetaDataEmit::DefineTypeDef`.|  
|[Метод TranslateSigWithScope](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-translatesigwithscope-method.md)|Импортирует сборку в текущую область и получает новую сигнатуру метаданных для Объединенной области.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейсы метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [Интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
