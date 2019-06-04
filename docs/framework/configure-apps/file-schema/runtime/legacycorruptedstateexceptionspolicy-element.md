---
title: Элемент <legacyCorruptedStateExceptionsPolicy>
ms.date: 03/30/2017
helpviewer_keywords:
- <legacyCorruptedStateExceptionsPolicy> element
- legacyCorruptedStateExceptionsPolicy element
ms.assetid: e0a55ddc-bfa8-4f3e-ac14-d1fc3330e4bb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6191ee2169a85725f0367763874e60c0ceb1d7a4
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2019
ms.locfileid: "66489432"
---
# <a name="legacycorruptedstateexceptionspolicy-element"></a>\<legacyCorruptedStateExceptionsPolicy > элемент
Указывает, допускает ли среда CLR управляемому коду перехватывать нарушения прав доступа и другие исключения поврежденного состояния.  
  
 \<configuration>  
\<Среда выполнения >  
\<legacyCorruptedStateExceptionsPolicy>  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<legacyCorruptedStateExceptionsPolicy enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`enabled`|Обязательный атрибут.<br /><br /> Указывает, что приложение будет перехватывать сбои поврежденного состояния исключение как нарушение прав доступа.|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|Значение|Описание|  
|-----------|-----------------|  
|`false`|Приложение не будет перехватывать сбои поврежденного состояния исключение как нарушение прав доступа. Это значение по умолчанию.|  
|`true`|Приложение будет перехватывать сбои поврежденного состояния исключение как нарушение прав доступа.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
  
## <a name="remarks"></a>Примечания  
 В .NET Framework версии 3.5 и более ранних версий среда CLR может управляемого кода для перехвата исключений, которые были вызваны поврежденных состояний процесса. Нарушение прав доступа является примером исключения этого типа.  
  
 Начиная с .NET Framework 4, управляемый код больше не перехватывает исключения в этих типов `catch` блоков. Тем не менее можно переопределить это изменение и продолжить обработку исключений поврежденного состояния двумя способами:  
  
- Задайте `<legacyCorruptedStateExceptionsPolicy>` элемента `enabled` атрибут `true`. Этот параметр конфигурации применяется целиком к процессу и влияет на все методы.  
  
 -или-  
  
- Применить <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> атрибут к методу, который содержит исключения `catch` блока.  
  
 Этот элемент конфигурации, доступны только в .NET Framework 4 и более поздних версий.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как указать, что приложение следует вернуться к поведению до .NET Framework 4 и перехватить все сбои поврежденного состояния исключения.  
  
```xml  
<configuration>  
   <runtime>  
      <legacyCorruptedStateExceptionsPolicy enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute>
- [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)
