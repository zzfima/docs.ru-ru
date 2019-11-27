---
title: Метод IMetaDataImport::EnumMembers
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMembers
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMembers
helpviewer_keywords:
- IMetaDataImport::EnumMembers method [.NET Framework metadata]
- EnumMembers method [.NET Framework metadata]
ms.assetid: 3fb8e178-342b-4c89-9bcf-f7f834e6cb77
topic_type:
- apiref
ms.openlocfilehash: acb772a64c8f13405f2836bb5f4f308986dce414
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447658"
---
# <a name="imetadataimportenummembers-method"></a>Метод IMetaDataImport::EnumMembers
Перечисляет токены MemberDef, представляющие члены указанного типа.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumMembers (   
   [in, out]  HCORENUM    *phEnum,   
   [in]  mdTypeDef   cl,   
   [out] mdToken     rMembers[],   
   [in]  ULONG       cMax,   
   [out] ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `phEnum`  
 [вход, выход] Указатель на перечислитель.  
  
 `cl`  
 окне Токен TypeDef, представляющий тип, элементы которого необходимо перечислить.  
  
 `rMembers`  
 заполняет Массив, используемый для хранения маркеров Мембердеф.  
  
 `cMax`  
 [in] Максимальный размер массива `rMembers`.  
  
 `pcTokens`  
 заполняет Фактическое число маркеров Мембердеф, возвращаемых в `rMembers`.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|`S_OK`|`EnumMembers` успешно возвращено.|  
|`S_FALSE`|Нет токенов Мембердеф для перечисления. В этом случае `pcTokens` равно нулю.|  
  
## <a name="remarks"></a>Примечания  
 При перечислении коллекций элементов для класса `EnumMembers` возвращает только элементы (поля и методы, но **не** свойства или события), определенные непосредственно в классе. Он не возвращает члены, наследуемые классом, даже если класс предоставляет реализацию для этих унаследованных членов. Чтобы перечислить унаследованные члены, вызывающий объект должен явно пройти по цепочке наследования. Обратите внимание, что правила для цепочки наследования могут различаться в зависимости от языка или компилятора, который выдал исходные метаданные.
 
 Свойства и события не перечисляются с помощью `EnumMembers`. Чтобы перечислить их, используйте [енумпропертиес](imetadataimport-enumproperties-method.md) или [EnumEvents](imetadataimport-enumevents-method.md).
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
