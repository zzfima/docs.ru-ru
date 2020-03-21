---
title: Элемент <loadFromRemoteSources>
ms.date: 05/24/2018
helpviewer_keywords:
- loadFromRemoteSources element
- <loadFromRemoteSources> element
ms.assetid: 006d1280-2ac3-4db6-a984-a3d4e275046a
ms.openlocfilehash: a0dcffe378cdd09de0fbd8f0a6ef0635c033fd9c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154066"
---
# <a name="loadfromremotesources-element"></a>\<loadFromRemoteSources> элемент
Уточняется, следует ли предоставить сборки, загруженные из удаленных источников, полное доверие к .NET Framework 4 и позже.
  
> [!NOTE]
> Если вы были направлены на эту статью из-за сообщения об ошибке в списке ошибок проекта Visual Studio или ошибки сборки, [см.](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee890038(v=vs.100))  
  
[**\<конфигурация>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<>выполнения**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<loadFromRemoteИсточники>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<loadFromRemoteSources
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Элементы и атрибуты
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|attribute|Описание|  
|---------------|-----------------|  
|`enabled`|Обязательный атрибут.<br /><br /> Уточняется, следует ли получить полное доверие сборке, загруженной из удаленного источника.|  
  
## <a name="enabled-attribute"></a>включенный атрибут  
  
|Значение|Описание|  
|-----------|-----------------|  
|`false`|Не доверяйте приложениям из удаленных источников. Это значение по умолчанию.|  
|`true`|Предоставляете полное доверие приложениям из удаленных источников.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о параметрах инициализации среды выполнения.|  
  
## <a name="remarks"></a>Remarks

В системе .NET 3.5 и более ранних версиях при загрузке сборки из удаленного местоположения код в сборке выполняется в частичном доверии с набором грантов, который зависит от зоны, из которой он загружается. Например, если вы загружаете сборку с веб-сайта, она загружается в интернет-зону и предоставляется набор разрешений в Интернете. Другими словами, он выполняет в интернет-песочнице.

Начиная с .NET Framework 4, политика безопасности доступа к кодам (CAS) отключена, а сборки загружаются в полном доверии. Обычно это дает полное доверие к сборкам, загруженным <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> методом, который ранее был песочницей. Чтобы предотвратить это, возможность запуска кода в сборках, загруженных из удаленного источника, отключена по умолчанию. По умолчанию при попытке загрузки <xref:System.IO.FileLoadException> удаленной сборки выбрасывается сообщение с исключением, подобное следующему:

```text
System.IO.FileNotFoundException: Could not load file or assembly 'file:assem.dll' or one of its dependencies. Operation is not supported.
(Exception from HRESULT: 0x80131515)
File name: 'file:assem.dll' --->
System.NotSupportedException: An attempt was made to load an assembly from a network location which would have caused the assembly
to be sandboxed in previous versions of the .NET Framework. This release of the .NET Framework does not enable CAS policy by default,
so this load may be dangerous. If this load is not intended to sandbox the assembly, please enable the loadFromRemoteSources switch.
```

Чтобы загрузить сборку и выполнить ее код, необходимо:

- Явно создайте песочницу для сборки (см. [Как: Выполнить частично доверенный код в песочнице).](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)

- Запустите код сборки в полном доверии. Вы делаете это путем `<loadFromRemoteSources>` настройки элемента. Это позволяет указать, что сборки, которые работают в частичном доверии к более ранним версиям рамочного соглашения .NET, теперь работают в полном доверии к .NET Framework 4 и более поздним версиям.

> [!IMPORTANT]
> Если сборка не должна выполняться в полном доверии, не устанавливайте этот элемент конфигурации. Вместо этого создайте песочницу, <xref:System.AppDomain> в которой можно загрузить сборку.

Атрибут `enabled` элемента `<loadFromRemoteSources>` эффективен только при отключении безопасности доступа к коду (CAS). По умолчанию политика CAS отключена в системе .NET 4 и более поздних версиях. Если вы `enabled` `true`установите, удаленные сборки получают полное доверие.

Если `enabled` не `true`установлен, <xref:System.IO.FileLoadException> то брошено под любым из следующих условий:

- Поведение текущего домена в песочнице отличается от его поведения в рамках .NET 3.5. Это требует, чтобы политика CAS была отключена, а текущий домен не был застечен на песочнице.

- Загрузка сборки не из `MyComputer` зоны.

Настройка `<loadFromRemoteSources>` элемента для `true` предотвращения этого исключения от броски. Это позволяет указать, что вы не полагаетесь на общее время выполнения языка в песочнице загруженных сборок для обеспечения безопасности, и что они могут быть разрешены для выполнения в полном доверии.

## <a name="notes"></a>Примечания

- В рамках .NET 4.5 и более поздних версиях сборки на локальных сетевых акциях работают в полном доверии по умолчанию; вы не должны включить `<loadFromRemoteSources>` элемент.

- Если приложение скопировано из Интернета, оно помечается ОС Windows как веб-приложение, даже если находится на локальном компьютере. Это обозначение можно изменить, изменив свойства файлов, или использовать `<loadFromRemoteSources>` элемент для предоставления сборке полного доверия. Также можно использовать метод <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A>, чтобы загрузить локальную сборку, которую операционная система пометила как загруженную из Интернета.

- Вы можете <xref:System.IO.FileLoadException> получить в приложении, которое работает в приложении Windows Virtual PC. Это может произойти при попытке загрузить файл из связанных папок на хостинг-компьютере. Это также может произойти при попытке загрузить файл из папки, связанной с [удаленными службами рабочего стола](/windows/win32/termserv/terminal-services-portal) (Terminal Services). Чтобы избежать исключения, `enabled` `true`установите на .

## <a name="configuration-file"></a>Файл конфигурации

Этот элемент обычно используется в файле конфигурации приложения, но может использоваться в других файлах конфигурации в зависимости от контекста. Для получения дополнительной информации смотрите статью [Подробнее о неявных использованиях политики CAS: loadFromRemoteSources](https://docs.microsoft.com/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources) в блоге .NET Security.  

## <a name="example"></a>Пример

Ниже приводится следующий пример, как предоставить полное доверие к сборкам, загруженным из удаленных источников.

```xml
<configuration>  
   <runtime>  
      <loadFromRemoteSources enabled="true"/>  
   </runtime>  
</configuration>  
```

## <a name="see-also"></a>См. также раздел

- [Более неявное использование политики CAS: loadFromRemoteSources](https://docs.microsoft.com/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources)
- [Практическое руководство. Выполнение не вполне безопасного кода в изолированной среде](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)
- [Схема параметров среды выполнения](index.md)
- [Схема конфигурации файлов](../index.md)
- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>
