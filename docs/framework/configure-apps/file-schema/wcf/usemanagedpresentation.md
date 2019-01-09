---
title: '&lt;useManagedPresentation&gt;'
ms.date: 03/30/2017
ms.assetid: 17a0dd77-af54-41db-a9d0-4b17ff42878f
ms.openlocfilehash: a60e1e16b9b41cc5df4ded51cc05d6109dd7b3dc
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54147711"
---
# <a name="ltusemanagedpresentationgt"></a>&lt;useManagedPresentation&gt;
Элемент привязки, используемый для связи со службой маркеров безопасности CardSpace, которая поддерживает CardSpace-профиль WS-Trust. Этот элемент не имеет атрибутов и представлен как пустой переключатель.  
  
 \<system.serviceModel >  
\<привязки >  
\<customBinding >  
\<Привязка >  
\<useManagedPresentation >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<useManagedPresentation />
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Отсутствует.  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Привязка >](../../../../../docs/framework/misc/binding.md)|Определяет все возможности пользовательской привязки.|  
  
## <a name="remarks"></a>Примечания  
 Этот элемент используется поставщиком удостоверения для отражения в своей политике поддержки CardSpace-профиля WS-Trust. Поставщики удостоверений, которые предоставляют такое утверждение политики, должны быть способны выдавать маркеры на основе этого профиля CardSpace.  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Configuration.UseManagedPresentationElement>  
 <xref:System.ServiceModel.Channels.UseManagedPresentationBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [Привязки](../../../../../docs/framework/wcf/bindings.md)  
 [Расширение привязок](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [Пользовательские привязки](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [\<customBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
