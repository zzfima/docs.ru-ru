---
title: '&lt;supportPortability&gt; элемент'
ms.date: 03/30/2017
helpviewer_keywords:
- supportPortability element
- <supportPortability> element
ms.assetid: 6453ef66-19b4-41f3-b712-52d0c2abc9ca
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4f1ceae32445fb350f6fcc98f3a1eec044fa7885
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54655508"
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
  
|Атрибут|Описание:|  
|---------------|-----------------|  
|PKT|Обязательный атрибут.<br /><br /> Указывает токен открытого ключа затрагиваемой сборки в виде строки.|  
|enabled|Необязательный атрибут.<br /><br /> Указывает, следует ли включить поддержку для обеспечения переносимости между реализациями заданной сборки .NET Framework.|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|Значение|Описание:|  
|-----------|-----------------|  
|true|Включите поддержку для обеспечения переносимости между реализациями заданной сборки .NET Framework. Это значение по умолчанию.|  
|False|Отключите поддержку переносимости между реализациями заданной сборки .NET Framework. Это позволяет приложению иметь ссылки на несколько реализаций заданной сборки.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
|`assemblyBinding`|Содержит сведения о перенаправлении версии сборки и о расположениях сборок.|  
  
## <a name="remarks"></a>Примечания  
 Начиная с версии [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], поддержка предоставляется автоматически для приложений, которые можно использовать один из двух реализаций .NET Framework, например либо реализации .NET Framework или .NET Framework для реализации Silverlight. Две реализации определенной сборки .NET Framework рассматриваются как эквивалент средством привязки сборок. В нескольких сценариях эта функция переносимости приложений вызывает проблемы. В этих случаях `<supportPortability>` элемент может использоваться, чтобы отключить эту функцию.  
  
 Одним из таких сценариев — это сборка, ссылки реализации .NET Framework и .NET Framework для реализации Silverlight определенной ссылочной сборки. Например конструктор XAML, записанных в Windows Presentation Foundation (WPF) может потребоваться Эталонная реализация оба рабочих стола WPF, для конструктора пользовательского интерфейса и для подмножества WPF, включенный в реализацию Silverlight. По умолчанию отдельные ссылки вызывают ошибку компиляции, так как привязка сборки видит две эквивалентные сборки. Этот элемент отключает поведение по умолчанию и позволяет завершить компиляцию.  
  
> [!IMPORTANT]
>  Чтобы компилятор для передачи информации в логику с привязкой сборки среды CLR, необходимо использовать `/appconfig` параметр компилятора, чтобы указать расположение файла app.config, содержащего данный элемент.  
  
## <a name="example"></a>Пример  
 В следующем примере включается приложению иметь ссылки на реализации .NET Framework и .NET Framework для реализации Silverlight любой сборки .NET Framework, существующей в обеих реализациях. `/appconfig` Необходимо использовать параметр компилятора, чтобы указать расположение этого файла app.config.  
  
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
- [/ appconfig (параметры компилятора C#)](../../../../../docs/csharp/language-reference/compiler-options/appconfig-compiler-option.md)
- [Общие сведения об унификации сборок .NET framework](https://msdn.microsoft.com/library/8d8cc65e-031d-463b-bde3-2c6dc2e3bc48)
