---
title: Элемент <enforceFIPSPolicy>
ms.date: 03/30/2017
helpviewer_keywords:
- enforceFIPSPolicy element
- FIPS
- <enforceFIPSPolicy> element
- Federal Information Processing Standards (FIPS)
ms.assetid: c35509c4-35cf-43c0-bb47-75e4208aa24e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b1aa958e15449949a1b7ca740198fff71295b2ad
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704973"
---
# <a name="enforcefipspolicy-element"></a>\<enforceFIPSPolicy > элемент
Указывает, нужно ли принудительно обеспечивать соблюдение требования конфигурации компьютера о том, что криптографические алгоритмы должны соответствовать стандартам FIPS.  
  
 \<Конфигурация > элемент  
\<Среда выполнения > элемент  
\<enforceFIPSPolicy > элемент  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<enforceFIPSPolicy enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|enabled|Обязательный атрибут.<br /><br /> Указывает, следует ли включить применение требования конфигурации компьютера, что необходимо соответствие стандарту FIPS алгоритмы шифрования.|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|Значение|Описание|  
|-----------|-----------------|  
|`true`|Если компьютер настроен требовать соответствовала стандарту FIPS алгоритмы шифрования, это требование применяется принудительно. Если класс реализует алгоритм, который не соответствует стандарту FIPS, конструкторы или `Create` методы для этого класса исключения, когда они запускаются на этом компьютере. Это значение по умолчанию.|  
|`false`|Алгоритмы шифрования, которые используются приложением не требуется соответствие стандарту FIPS, независимо от конфигурации компьютера.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
  
## <a name="remarks"></a>Примечания  
 Начиная с .NET Framework 2.0, создания классов, которые реализуют алгоритмы шифрования управляет конфигурацией компьютера. Если компьютер настроен требовать соответствие стандарту FIPS алгоритмы, а класс реализует алгоритм, который не соответствует стандарту FIPS, любая попытка создать экземпляр этого класса создает исключение. Конструкторы вызывать <xref:System.InvalidOperationException> исключение, и `Create` методы вызывают исключение <xref:System.Reflection.TargetInvocationException> исключение с внутренним <xref:System.InvalidOperationException> исключение.  
  
 Если ваше приложение выполняется на компьютерах, если их конфигурация требуют соответствия стандарту FIPS, а приложение использует алгоритм, который не соответствует стандарту FIPS, можно использовать этот элемент в файле конфигурации для предотвращения среда CLR (CLR) из обеспечение соответствия FIPS. Этот элемент был введен в [!INCLUDE[net_v20SP1_long](../../../../../includes/net-v20sp1-long-md.md)].  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как помешать среде CLR обеспечивать соответствие требованиям FIPS применения.  
  
```xml  
<configuration>  
    <runtime>  
        <enforceFIPSPolicy enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [Модель криптографии](../../../../../docs/standard/security/cryptography-model.md)
