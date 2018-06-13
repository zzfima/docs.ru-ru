---
title: Метод IMetaDataImport::EnumMethodSemantics
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethodSemantics
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethodSemantics
helpviewer_keywords:
- EnumMethodSemantics method [.NET Framework metadata]
- IMetaDataImport::EnumMethodSemantics method [.NET Framework metadata]
ms.assetid: e7e3c630-9691-46d6-94df-b5593a7bb08a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 00a28e0f7ab03af8d5f2fc0dda5274f9aaa4dca2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449099"
---
# <a name="imetadataimportenummethodsemantics-method"></a>Метод IMetaDataImport::EnumMethodSemantics
Перечисляет свойства и события их изменения, с которыми связан указанный метод.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT EnumMethodSemantics (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,   
   [out] mdToken         rEventProp[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcEventProp  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `phEnum`  
 [in, out] Указатель на перечислитель. Это должно быть NULL при первом вызове этого метода.  
  
 `mb`  
 [in] Токен MethodDef, который ограничивает область перечисления.  
  
 `rEventProp`  
 [out] Массив, используемый для хранения события или свойства.  
  
 `cMax`  
 [in] Максимальный размер массива `rEventProp`.  
  
 `pcEventProp`  
 [out] Количество событий или свойств, возвращаемых в `rEventProp`.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|`S_OK`|`EnumMethodSemantics` успешно возвращен.|  
|`S_FALSE`|Отсутствуют события и свойства для перечисления. В этом случае `pcEventProp` равно нулю.|  
  
## <a name="remarks"></a>Примечания  
 Определение много типами среды CLR *свойство* `Changed` событий и `On` *свойство* `Changed` методы, относящиеся к их свойствам. Например <xref:System.Windows.Forms.Control?displayProperty=nameWithType> определяет тип <xref:System.Windows.Forms.Control.Font%2A> свойства <xref:System.Windows.Forms.Control.FontChanged> события и <xref:System.Windows.Forms.Control.OnFontChanged%2A> метод. Метод доступа set <xref:System.Windows.Forms.Control.Font%2A> вызовы свойство <xref:System.Windows.Forms.Control.OnFontChanged%2A> метод, который в свою очередь вызывает <xref:System.Windows.Forms.Control.FontChanged> событий. Вызовите `EnumMethodSemantics` с помощью MethodDef для <xref:System.Windows.Forms.Control.OnFontChanged%2A> для получения ссылок на <xref:System.Windows.Forms.Control.Font%2A> свойство и <xref:System.Windows.Forms.Control.FontChanged> событий.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
