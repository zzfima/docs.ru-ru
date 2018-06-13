---
title: '&lt;supportPortability&gt; элемент'
ms.date: 03/30/2017
helpviewer_keywords:
- supportPortability element
- <supportPortability> element
ms.assetid: 6453ef66-19b4-41f3-b712-52d0c2abc9ca
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0a8a454919a195a0f0c03ed6890e51b2723f64fb
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32754110"
---
# <a name="ltsupportportabilitygt-element"></a>&lt;supportPortability&gt; элемент
Указывает, что приложение может ссылаться на ту же сборку в двух различных реализациях .NET Framework, отключая поведение по умолчанию, которое рассматривает сборки как эквивалент для переносимости приложения.  
  
 \<Конфигурация > элемент  
\<Среда выполнения > элемент  
\<assemblyBinding > элемент  
\<supportPortability > элемент  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<supportPortability PKT="public_key_token" enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|PKT|Обязательный атрибут.<br /><br /> Указывает токен открытого ключа затронутых сборки в виде строки.|  
|enabled|Необязательный атрибут.<br /><br /> Указывает, следует ли включить поддержку переносимости между реализациями заданной сборки платформы .NET Framework.|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|Значение|Описание|  
|-----------|-----------------|  
|true|Включите поддержку переносимости между реализациями заданной сборки платформы .NET Framework. Это значение по умолчанию.|  
|False|Отключите поддержку переносимости между реализациями заданной сборки платформы .NET Framework. Это позволяет приложению иметь ссылки на несколько реализаций указанной сборки.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
|`assemblyBinding`|Содержит сведения о перенаправлении версии сборки и о расположениях сборок.|  
  
## <a name="remarks"></a>Примечания  
 Начиная с версии [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], автоматически обеспечивается для приложений, которые можно использовать любой из двух реализации платформы .NET Framework, например реализации .NET Framework или .NET Framework для Silverlight реализации. Две реализации определенной сборки .NET Framework рассматриваются как эквивалент связывателя сборок. В нескольких сценариях эта функция переносимости приложений вызывает проблемы. В этих сценариях `<supportPortability>` элемент может использоваться, чтобы отключить эту функцию.  
  
 Одним из таких сценариев — это сборка, имеется ссылка в реализации .NET Framework и платформе .NET Framework для Silverlight определенной ссылочной сборки реализации. Например конструктор XAML, записанных в Windows Presentation Foundation (WPF) может потребоваться эталонной реализации обоих WPF Desktop, пользовательский интерфейс конструктора и подмножество WPF, включенный в реализации Silverlight. По умолчанию отдельные ссылки вызывают ошибку компиляции, так как привязка сборки видит две эквивалентные сборки. Этот элемент отключает поведение по умолчанию и разрешает завершить компиляцию.  
  
> [!IMPORTANT]
>  Чтобы компилятор для передачи сведений в логику привязки сборки среды CLR, необходимо использовать `/appconfig` параметр компилятора для указания расположения файла app.config, содержащего этот элемент.  
  
## <a name="example"></a>Пример  
 Следующий пример позволяет приложению иметь ссылки на реализации .NET Framework и платформе .NET Framework для Silverlight реализации любой сборки .NET Framework, существует в обоих реализациях. `/appconfig` Необходимо использовать параметр компилятора для указания расположения этого файла app.config.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding>  
         <supportPortability PKT="7cec85d7bea7798e" enable="false"/>  
         <supportPortability PKT="31bf3856ad364e35" enable="false"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также  
 [/ appconfig (параметры компилятора C#)](http://msdn.microsoft.com/library/ee523958.aspx)  
 [Общие сведения о унификации сборок .NET framework](http://msdn.microsoft.com/library/8d8cc65e-031d-463b-bde3-2c6dc2e3bc48)
