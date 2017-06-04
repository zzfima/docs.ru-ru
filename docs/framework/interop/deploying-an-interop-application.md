---
title: "Deploying an Interop Application | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "deploying applications [.NET Framework], interop"
  - "strong-named assemblies, interop applications"
  - "unsigned assemblies"
  - "private assemblies"
  - "exposing COM components to .NET Framework"
  - "interoperation with unmanaged code, deploying applications"
  - "shared assemblies"
  - "COM interop, deploying applications"
  - "interoperation with unmanaged code, exposing COM components"
  - "signed assemblies"
  - "COM interop, exposing COM components"
ms.assetid: ea8a403e-ae03-4faa-9d9b-02179ec72992
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# Deploying an Interop Application
Обычно приложение взаимодействия включает сборку клиента .NET, одну или несколько сборок взаимодействия, предоставляющих различные библиотеки COM\-типов, и один или несколько зарегистрированных COM\-компонентов.  Visual Studio и [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] включают средства для импорта и преобразования библиотек типов в сборки взаимодействия согласно описанию в разделе [Importing a Type Library as an Assembly](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md).  Есть два способа развертывания приложения взаимодействия:  
  
-   С использованием встроенных типов взаимодействия: начиная с платформы [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], можно указать компилятору, что в исполняемый файл следует внедрить информацию о типах из сборки взаимодействия.  Компилятор встраивает информацию только о типах, используемых приложением.  Развертывать сборку взаимодействия вместе с приложением не требуется.  Это рекомендуемая методика.  
  
-   Путем развертывания сборок взаимодействия: можно создать стандартную ссылку на сборку взаимодействия.  В данном случае сборку взаимодействия следует развернуть вместе с приложением.  Если применяется данный метод и не используется частный COM\-компонент, необходимо во всех случаях ссылаться на основную сборку взаимодействия, опубликованную автором COM\-компонента, который планируется интегрировать в управляемый код.  Дополнительные сведения о создании и использовании основных сборок взаимодействия см. в разделе [Основные сборки взаимодействия](http://msdn.microsoft.com/ru-ru/b977a8be-59a0-40a0-a806-b11ffba5c080).  
  
 В случае использования встраивания типов взаимодействия развертывание выполняется просто и удобно.  Никаких дополнительных действий не требуется.  В оставшейся части этой статьи описаны сценарии развертывания сборок взаимодействия с приложением.  
  
## Развертывание сборок взаимодействия  
 Сборки могут иметь строгие имена.  Сборка со строгим именем содержит открытый ключ издателя, который обеспечивает уникальность идентификации.  Сборки, формируемые [программой импорта библиотек типов \(Tlbimp.exe\)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md), могут быть подписаны издателем с помощью параметра **\/keyfile**.  Подписанные сборки можно установить в глобальный кэш сборок.  Неподписанные сборки должны быть установлены на компьютере пользователя как закрытые сборки.  
  
### Закрытые сборки  
 При установке сборки для закрытого использования исполняемый файл и сборка взаимодействия приложения, содержащая импортированные типы COM, должны располагаться в одной структуре каталогов.  На следующей иллюстрации показана неподписанная сборка взаимодействия, которая должна использоваться закрытым образом приложениями Client1.exe и Client2.exe, расположенными в отдельных каталогах приложений.  Сборка взаимодействия, называющаяся LOANLib.dll в этом примере, установлена дважды.  
  
 ![Структура папки и реестр Windows](../../../docs/framework/interop/media/comdeployprivate.gif "comdeployprivate")  
Структура каталогов и записи реестра для закрытого развертывания  
  
 Все COM\-компоненты, связанные с приложением, должны быть зарегистрированы в системном реестре Windows.  Если приложения Client1.exe и Client2.exe, показанные на иллюстрации, установлены на разных компьютерах, COM\-компоненты должны быть зарегистрированы на обоих компьютерах.  
  
### Общие сборки  
 Сборки, совместно используемые несколькими приложениями, должны устанавливаться в централизованном репозитории, который называется глобальным кэшем сборок.  Если сборка взаимодействия подписана и установлена в глобальном кэше сборок, клиенты .NET могут обращаться к одной и той же ее копии.  Дополнительные сведения о создании и использовании основных сборок взаимодействия см. в разделе [Основные сборки взаимодействия](http://msdn.microsoft.com/ru-ru/b977a8be-59a0-40a0-a806-b11ffba5c080).  
  
## См. также  
 [Exposing COM Components to the .NET Framework](../../../docs/framework/interop/exposing-com-components.md)   
 [Importing a Type Library as an Assembly](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md)   
 [Using COM Types in Managed Code](http://msdn.microsoft.com/ru-ru/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66)   
 [Compiling an Interop Project](../../../docs/framework/interop/compiling-an-interop-project.md)