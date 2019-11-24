---
title: Интерфейс IMetaDataImport
ms.date: 03/30/2017
api_name:
- IMetaDataImport
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport
helpviewer_keywords:
- IMetaDataImport interface [.NET Framework metadata]
ms.assetid: 0adbbd35-5e8d-4fec-8268-dc70a07c5975
topic_type:
- apiref
ms.openlocfilehash: 2d45a369def193b9c8d8f9a3aa954ede600a87dd
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434740"
---
# <a name="imetadataimport-interface"></a>Интерфейс IMetaDataImport
Предоставляет методы для импорта существующих метаданных из переносимого исполняемого (PE) файла или другого источника, такого как библиотека типов или отдельный двоичный файл метаданных среды выполнения, а также управления этим метаданными.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод CloseEnum](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-closeenum-method.md)|Закрывает перечислитель с указанным дескриптором.|  
|[Метод CountEnum](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-countenum-method.md)|Возвращает число элементов в перечислителе с указанным дескриптором.|  
|[Метод EnumCustomAttributes](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumcustomattributes-method.md)|Перечисляет список токенов определений настраиваемых атрибутов, связанных с указанным типом или членом.|  
|[Метод EnumEvents](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumevents-method.md)|Перечисляет токены определений событий для указанного токена TypeDef.|  
|[Метод EnumFields](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumfields-method.md)|Перечисляет токены FieldDef для типа, на который ссылается указанный токен TypeDef.|  
|[Метод EnumFieldsWithName](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumfieldswithname-method.md)|Перечисляет токены FieldDef заданного типа с указанным именем.|  
|[Метод EnumInterfaceImpls](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enuminterfaceimpls-method.md)|Перечисляет токены MethodDef, представляющие реализации интерфейса.|  
|[Метод EnumMemberRefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummemberrefs-method.md)|Перечисляет токены MemberRef, представляющие члены указанного типа.|  
|[Метод EnumMembers](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummembers-method.md)|Перечисляет токены MemberDef, представляющие члены указанного типа.|  
|[Метод EnumMembersWithName](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummemberswithname-method.md)|Перечисляет токены MemberDef, представляющие члены указанного типа с заданным именем.|  
|[Метод EnumMethodImpls](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummethodimpls-method.md)|Перечисляет токены MethodBody и MethodDeclaration, представляющие методы указанного типа.|  
|[Метод EnumMethods](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummethods-method.md)|Перечисляет токены MethodDef, представляющие методы указанного типа.|  
|[Метод EnumMethodSemantics](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummethodsemantics-method.md)|Перечисляет свойства и события их изменения, с которыми связан указанный метод.|  
|[Метод EnumMethodsWithName](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummethodswithname-method.md)|Перечисляет методы с заданным именем, определяемые по типу, на который ссылается указанный токен TypeDef.|  
|[Метод EnumModuleRefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummodulerefs-method.md)|Перечисляет токены ModuleRef, представляющие импортируемые модули.|  
|[Метод EnumParams](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumparams-method.md)|Перечисляет токены ParamDef, представляющие параметры метода, на который ссылается указанный токен MethodDef.|  
|[Метод EnumPermissionSets](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumpermissionsets-method.md)|Перечисляет разрешения для объектов в указанной области метаданных.|  
|[Метод EnumProperties](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumproperties-method.md)|Перечисляет токены PropertyDef, представляющие свойства типа, на который ссылается указанный токен TypeDef.|  
|[Метод EnumSignatures](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumsignatures-method.md)|Перечисляет токены Signature, представляющие отдельные подписи в текущей области.|  
|[Метод EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)|Перечисляет токены TypeDef, представляющие все типы в текущей области.|  
|[Метод EnumTypeRefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtyperefs-method.md)|Перечисляет токены TypeRef, определенные в текущей области метаданных.|  
|[Метод EnumTypeSpecs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypespecs-method.md)|Перечисляет токены TypeSpec, определенные в текущей области метаданных.|  
|[Метод EnumUnresolvedMethods](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumunresolvedmethods-method.md)|Перечисляет токены MemberDef, представляющие неразрешенные методы в текущей области метаданных.|  
|[Метод EnumUserStrings](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumuserstrings-method.md)|Перечисляет токены String, представляющие жестко заданные строки в текущей области метаданных.|  
|[Метод FindField](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md)|Возвращает токен FieldDef для поля, являющегося членом заданного типа и обладающего указанными именем и подписью метаданных.|  
|[Метод FindMember](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmember-method.md)|Возвращает указатель на токен MemberDef для члена, определенного заданным типом, с указанными именем и подписью метаданных.|  
|[Метод FindMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmemberref-method.md)|Возвращает указатель на токен MemberRef для члена, определенного заданным типом, с указанными именем и подписью метаданных.|  
|[Метод FindMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md)|Возвращает указатель на токен MethodDef для метода, определенного заданным типом, с указанными именем и подписью метаданных.|  
|[Метод FindTypeDefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findtypedefbyname-method.md)|Возвращает указатель на токен метаданных TypeDef для типа с указанным именем.|  
|[Метод FindTypeRef](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findtyperef-method.md)|Возвращает указатель на токен метаданных TypeRef, который ссылается на тип в заданной области поиска с указанным именем.|  
|[Метод GetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getclasslayout-method.md)|Возвращает сведения о структуре для класса, на который ссылается указанный токен TypeDef.|  
|[Метод GetCustomAttributeByName](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getcustomattributebyname-method.md)|Возвращает значение настраиваемого атрибута по указанному имени.|  
|[Метод GetCustomAttributeProps](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getcustomattributeprops-method.md)|Возвращает значение пользовательского атрибута по указанному токену метаданных.|  
|[Метод GetEventProps](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-geteventprops-method.md)|Возвращает сведения о метаданных (включая объявленный тип, методы добавления и удаления для делегатов, а также всевозможные флаги и другие связанные с ними данные) для события, представленного указанным токеном события.|  
|[Метод GetFieldMarshal](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getfieldmarshal-method.md)|Возвращает указатель на машинный неуправляемый тип поля, представленного заданным токеном метаданных Field.|  
|[Метод GetFieldProps](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getfieldprops-method.md)|Возвращает метаданные, связанные с полем, на которое ссылается указанный токен FieldDef.|  
|[Метод GetInterfaceImplProps](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getinterfaceimplprops-method.md)|Возвращает указатель на токены метаданных для типа, который реализует заданный метод, и интерфейса, который объявляет этот метод.|  
|[Метод GetMemberProps](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getmemberprops-method.md)|Возвращает сведения о метаданных (в том числе имя, двоичную подпись и относительный виртуальный адрес) члена типа, на который ссылается указанный токен метаданных.|  
|[Метод GetMemberRefProps](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getmemberrefprops-method.md)|Возвращает метаданные, связанные с членом, на который ссылается указанный токен.|  
|[Метод GetMethodProps](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getmethodprops-method.md)|Возвращает метаданные, связанные с методом, на который ссылается указанный токен MethodDef.|  
|[Метод GetMethodSemantics](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getmethodsemantics-method.md)|Возвращает указатель на взаимосвязь между методом, на который ссылается заданный токен MethodDef, и парой, состоящей из свойства и события, на которую ссылается заданный токен EventProp.|  
|[Метод GetModuleFromScope](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getmodulefromscope-method.md)|Возвращает указатель на токен метаданных для модуля, ссылка на который содержится в текущей области метаданных.|  
|[Метод GetModuleRefProps](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getmodulerefprops-method.md)|Возвращает имя модуля, на который ссылается указанный токен метаданных.|  
|[Метод GetNameFromToken](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getnamefromtoken-method.md)|Возвращает имя объекта, на который ссылается указанный токен метаданных, в формате UTF-8.|  
|[Метод GetNativeCallConvFromSig](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getnativecallconvfromsig-method.md)|Возвращает собственное соглашение о вызовах для метода, представленного заданным указателем на подпись.|  
|[Метод GetNestedClassProps](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getnestedclassprops-method.md)|Возвращает токен TypeDef для включающего родительского типа заданного вложенного типа.|  
|[Метод GetParamForMethodIndex](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getparamformethodindex-method.md)|Возвращает указатель на токен, представляющий параметр с заданным порядковым номером в последовательности параметров метода, представленного указанным токеном MethodDef.|  
|[Метод GetParamProps](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getparamprops-method.md)|Возвращает значения метаданных для параметра, на который ссылается указанный токен ParamDef.|  
|[Метод GetPermissionSetProps](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getpermissionsetprops-method.md)|Возвращает метаданные, связанные с набором разрешений System.Security.PermissionSet, который представлен указанным токеном Permission.|  
|[Метод GetPinvokeMap](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getpinvokemap-method.md)|Возвращает токен ModuleRef, представляющий целевую сборку вызова PInvoke.|  
|[Метод GetPropertyProps](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getpropertyprops-method.md)|Возвращает метаданные, связанные со свойством, представленным указанным токеном.|  
|[Метод GetRVA](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getrva-method.md)|Возвращает смещение относительного виртуального адреса объекта кода, представленного указанным токеном.|  
|[Метод GetScopeProps](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getscopeprops-method.md)|Возвращает имя и при необходимости идентификатор версии сборки или модуля в текущей области метаданных.|  
|[Метод GetSigFromToken](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getsigfromtoken-method.md)|Возвращает двоичную подпись метаданных, связанную с указанным токеном.|  
|[Метод GetTypeDefProps](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-gettypedefprops-method.md)|Возвращает сведения о метаданных для типа, представленного указанным токеном TypeDef.|  
|[Метод GetTypeRefProps](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-gettyperefprops-method.md)|Возвращает метаданные, связанные с типом, на который ссылается указанный токен TypeRef.|  
|[Метод GetTypeSpecFromToken](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-gettypespecfromtoken-method.md)|Возвращает двоичную подпись метаданных для спецификации типа, представленного указанным токеном.|  
|[Метод GetUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getuserstring-method.md)|Получает строку литералов, представленную указанным токеном метаданных.|  
|[Метод IsGlobal](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-isglobal-method.md)|Возвращает значение, указывающее на наличие глобальной области у поля, метода или типа, представленного заданным токеном метаданных.|  
|[Метод IsValidToken](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-isvalidtoken-method.md)|Возвращает значение, указывающее, содержится ли в заданном токене допустимая ссылка на объект кода.|  
|[Метод ResetEnum](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-resetenum-method.md)|Возвращает заданный перечислитель в указанную позицию.|  
|[Метод ResolveTypeRef](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-resolvetyperef-method.md)|Возвращает сведения о типе, на который ссылается указанный токен TypeRef.|  
  
## <a name="remarks"></a>Заметки  
 По своей структуре интерфейс `IMetaDataImport` предназначен в первую очередь для использования средствами и службами, которые будут импортировать сведения о типах (например, средства разработки) или управлять компонентами развертывания (например, службы разрешения или активации). Методы интерфейса `IMetaDataImport` делятся по задачам на следующие категории:  
  
- перечисление коллекций элементов в области метаданных;  
  
- поиск элементов с определенным набором характеристик;  
  
- получение свойств указанного элемента;  
  
- методы Get предназначены специально для возврата свойств с одним значением для элемента метаданных. Если свойство ссылается на другой элемент, возвращается токен этого элемента. Любой тип ввода указателя может иметь значение NULL, свидетельствующее о том, что определенное значение не запрашивается. Для получения свойств, которые по сути являются объектами коллекции (например, коллекции интерфейсов, реализуемых классом), используются методы перечисления.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Library:** Used as a resource in MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
