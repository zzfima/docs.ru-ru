---
title: '&lt;shadowCopyVerifyByTimestamp&gt; элемент'
ms.date: 03/30/2017
helpviewer_keywords:
- <shadowCopyTimeStampVerification> element
- shadowCopyTimeStampVerification element
ms.assetid: 2f1648e5-997b-435e-a4f9-d236c574c66c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2439a4812163562a73bd3520e65b9973e666a863
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltshadowcopyverifybytimestampgt-element"></a>&lt;shadowCopyVerifyByTimestamp&gt; элемент
Указывает, использует ли теневое копирование поведение при запуске по умолчанию, представленное в [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], или возвращается к поведению при запуске, используемому в предыдущих версиях .NET Framework.  
  
 \<Конфигурация > элемент  
\<Среда выполнения > элемент  
\<shadowCopyVerifyByTimestamp > элемент  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<shadowCopyVerifyByTimestamp enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|enabled|Обязательный атрибут.<br /><br /> Указывает ли домены приложений, использующих теневое копирование сравнивать отметки времени сборок при запуске, чтобы определить, обновляется ли сборки перед теневым копированием.|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|Значение|Описание|  
|-----------|-----------------|  
|true|При запуске копируются только сборки, которые были обновлены с момента последнего копирования в каталог теневого копирования. Это значение по умолчанию для [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].|  
|False|Возвращается к поведению при запуске предыдущих версий платформы .NET Framework, который был для копирования всех файлов во время запуска.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
  
## <a name="remarks"></a>Примечания  
 Начиная с [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], выполняется теневое копирование только в том случае, если их отметки времени показывают, что они были изменены с момента последнего копирования в каталог теневого копирования сборок. Это сокращает время запуска для многих приложений, использующих теневое копирование, как описано в [теневое копирование сборок](../../../../../docs/framework/app-domains/shadow-copy-assemblies.md). Для приложений с большим процентом и высокой частотой обновления сборок это изменение в поведении может не быть выгодно. В этом случае можно использовать этот элемент для восстановления поведения предыдущих версий платформы .NET Framework.  
  
## <a name="example"></a>Пример  
 Приведенный ниже показано, как отключить поведение по умолчанию при запуске теневое копирование в [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]и вернуться к поведению при запуске предыдущих версий платформы .NET Framework.  
  
```xml  
<configuration>  
   <runtime>  
      <shadowCopyVerifyByTimestamp enabled="false" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также  
 [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [Теневое копирование сборок](../../../../../docs/framework/app-domains/shadow-copy-assemblies.md)
