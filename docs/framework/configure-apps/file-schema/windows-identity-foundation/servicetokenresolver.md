---
title: "&lt;serviceTokenResolver&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
caps.latest.revision: 8
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 7
---
# &lt;serviceTokenResolver&gt;
Регистрирует Распознавателю маркеров службы, используемые в коллекцию обработчиков маркеров обработчики.  Распознавателю маркеров службы используется для разрешения маркера шифрования на входящих токенов и сообщения.  
  
## Синтаксис  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <serviceTokenResolver type=xs:string>  
        </serviceTokenResolver>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние элементы и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|type|Указывает тип службы Распознавателю маркеров.  Либо <xref:System.IdentityModel.Selectors.SecurityTokenResolver> тип или тип, производный от <xref:System.IdentityModel.Selectors.SecurityTokenResolver> класса.  Дополнительные сведения об указании `type` атрибута см [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md#BKMK_CustomTypeReferences).  Обязательный.|  
  
### Дочерние элементы  
 None  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<securityTokenHandlerConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Содержит настройки для коллекции безопасности обработчиков маркеров.|  
  
## Заметки  
 Распознавателю маркеров службы можно использовать для разрешения маркера шифрования на входящих токенов и сообщения.  Он используется для извлечения ключа, который должен использоваться для расшифровки входящие маркеры.  Необходимо указать `type` атрибут.  Может быть указан тип <xref:System.IdentityModel.Selectors.SecurityTokenResolver> или пользовательского типа, производного от <xref:System.IdentityModel.Selectors.SecurityTokenResolver> класса.  
  
 Некоторые обработчики маркеров позволяют задать параметры службы Распознавателю маркеров в конфигурации.  Параметры на отдельных обработчиков маркеров вместо указанной коллекции обработчик маркеров безопасности.  
  
> [!NOTE]
>  Указание `<serviceTokenResolver>` элемент как дочерний элемент [\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) элемент является устаревшим, но по\-прежнему поддерживается для обратной совместимости.  Параметры на `<securityTokenHandlerConfiguration>` элементов заменяют на `<identityConfiguration>` элемент.  
  
## Пример  
  
```  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```