---
title: Элемент <generatePublisherEvidence>
ms.date: 03/30/2017
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
ms.openlocfilehash: 24a5ea02992a5bce681b5bab4fb7f75505bd225d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154118"
---
# <a name="generatepublisherevidence-element"></a>\<Элемент generatePublisherEvidence>
Уточняется, создает <xref:System.Security.Policy.Publisher> ли время выполнения доказательства безопасности доступа к коду (CAS).  
  
[**\<конфигурация>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<>выполнения**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<генерироватьPublisherEvidence>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<generatePublisherEvidence
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|attribute|Описание|  
|---------------|-----------------|  
|`enabled`|Обязательный атрибут.<br /><br /> Уточняется, создает <xref:System.Security.Policy.Publisher> ли время выполнения доказательства.|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|Значение|Описание|  
|-----------|-----------------|  
|`false`|Не создает <xref:System.Security.Policy.Publisher> доказательств.|  
|`true`|Создает <xref:System.Security.Policy.Publisher> доказательства. Это значение по умолчанию.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о параметрах инициализации среды выполнения.|  
  
## <a name="remarks"></a>Remarks  
  
> [!NOTE]
> В рамках .NET 4 и позже этот элемент не влияет на время сборки. Для получения дополнительной информации смотрите раздел "Упрощение политики [безопасности" в разделе "Изменения безопасности".](../../../security/security-changes.md)  
  
 Общее время выполнения языка (CLR) пытается проверить подпись Authenticode <xref:System.Security.Policy.Publisher> во время загрузки, чтобы создать улики для сборки. Однако по умолчанию большинству <xref:System.Security.Policy.Publisher> приложений не нужны доказательства. Стандартная политика CAS не <xref:System.Security.Policy.PublisherMembershipCondition>опирается на . Следует избегать ненужных затрат на запуск, связанных с проверкой подписи издателя, если приложение не <xref:System.Security.Permissions.PublisherIdentityPermission> выполняется на компьютере с пользовательской политикой CAS или не намерено удовлетворять требования в среде частичного доверия. (Требования к разрешению на идентификацию всегда удались в условиях полного доверия.)  
  
> [!NOTE]
> Мы рекомендуем службам `<generatePublisherEvidence>` использовать элемент для повышения производительности запуска.  Использование этого элемента также может помочь избежать задержек, которые могут привести к тайм-ауту и отмене запуска службы.  
  
## <a name="configuration-file"></a>Файл конфигурации  
 Этот элемент может быть использован только в файле конфигурации приложения.  
  
## <a name="example"></a>Пример  
 Ниже приводится следующий `<generatePublisherEvidence>` пример, как использовать элемент для отсеивания проверки политики издателя CAS для приложения.  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также раздел

- [Схема параметров среды выполнения](index.md)
- [Схема конфигурации файлов](../index.md)
