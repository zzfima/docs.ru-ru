---
title: "How to: Create COM Wrappers | Microsoft Docs"
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
  - "COM,wrappers creating"
  - "COM,wrappers Visual Studio"
ms.assetid: bdf89bea-1623-45ee-a57b-cf7c90395efa
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# How to: Create COM Wrappers
Для создания оболочек модели COM можно использовать возможности [!INCLUDE[vsprvsext](../../../includes/vsprvsext-md.md)] или программы Tlbimp.exe и Regasm.exe платформы .NET Framework.  Оба метода создают два типа оболочек COM:  
  
-   [Runtime Callable Wrapper](../../../docs/framework/interop/runtime-callable-wrapper.md) из библиотеки типов для выполнения COM\-объекта в управляемом коде.  
  
-   [COM Callable Wrapper](../../../docs/framework/interop/com-callable-wrapper.md) с необходимыми настройками реестра для выполнения управляемого объекта в собственном приложении платформы.  
  
 В [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] разработчик может добавить оболочку COM в качестве ссылки в свой проект.  
  
## Инкапсуляция COM\-объектов в управляемом приложении  
  
#### Создание вызываемой оболочки времени выполнения с помощью Visual Studio  
  
1.  Откройте проект в своем управляемом приложении.  
  
2.  В меню **Проект** выберите команду **Показать все файлы**.  
  
3.  В меню **Проект** щелкните команду **Добавить ссылку**.  
  
4.  В диалоговом окне "Добавление ссылки" щелкните вкладку **COM**, выберите нужный компонент и нажмите кнопку **OK**.  
  
     В окне **Обозреватель решения** обратите внимание, что COM\-компонент добавляется в папку "Ссылки" текущего проекта.  
  
 Теперь разработчик может создать код для доступа к COM\-объекту.  Можно начать с объявления объекта, например с помощью инструкции `Imports` для [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)] или инструкции `Using` для [!INCLUDE[csprcslong](../../../includes/csprcslong-md.md)].  
  
> [!NOTE]
>  Если нужно запрограммировать компоненты Microsoft Office сначала установите [Основные сборки взаимодействия Microsoft Office](http://go.microsoft.com/fwlink/?LinkId=50479) из Центра загрузки Майкрософт.  На этапе 4 выберите самую новую версию библиотеки объектов, доступную для нужного продукта Office, например библиотеку **Microsoft Word 11.0 Object Library**.  [](http://msdn.microsoft.com/ru-ru/c9d2a8b9-69df-4c0b-90ca-4d85bae063c4)  
  
#### Создание вызываемой оболочки времени выполнения с помощью программ .NET Framework  
  
-   Запустите программу [Tlbimp.exe \(Type Library Importer\)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md).  
  
 Эта программа создает сборку, содержащую метаданные времени выполнения для типов, определенных в исходной библиотеке типов.  
  
## Инкапсуляция управляемых объектов в собственное представление платформы  
  
#### Создание вызываемой оболочки COM с помощью Visual Studio  
  
1.  Создайте проект библиотеки классов для управляемого класса, который нужно использовать в собственном коде платформы.  У класса должен быть конструктор по умолчанию.  
  
     Убедитесь, что файл AssemblyInfo содержит полный номер версии создаваемой сборки, состоящий из четырех частей.  Это число необходимо для управления версиями в реестре Windows.  Дополнительные сведения о номерах версий см. в разделе [Управление версиями сборок](../../../docs/framework/app-domains/assembly-versioning.md).  
  
2.  В меню **Проект** выберите пункт **Свойства**.  
  
3.  Перейдите на вкладку **Compile**.  
  
4.  Установите флажок **Регистрация для COM\-взаимодействия**.  
  
 При построении проекта сборка автоматически регистрируется для COM\-взаимодействия.  При построении собственного приложения платформы в [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] разработчик может использовать сборку, выбрав **Добавить ссылку** в меню **Проект**.  
  
#### Создание вызываемой оболочки COM с помощью программ .NET Framework  
  
-   Запустите программу [Regasm.exe \(Assembly Registration Tool\)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md).  
  
 Эта программа читает метаданные сборки и добавляет в реестр необходимые записи.  В результате COM\-клиенты могут прозрачно создавать классы .NET Framework.  Сборку можно использовать, как если бы это был собственный COM\-класс.  
  
 Программу Regasm.exe можно выполнить для сборки, находящейся в любом каталоге, а затем выполнить [Gacutil.exe \(Global Assembly Cache Tool\)](../../../docs/framework/tools/gacutil-exe-gac-tool.md), чтобы переместить сборку в глобальный кэш сборок.  Перемещение сборки не делает недействительными записи о местонахождении в реестре, так как глобальный кэш сборок всегда проверяет, не находится ли сборка где\-нибудь еще.  
  
## См. также  
 [Runtime Callable Wrapper](../../../docs/framework/interop/runtime-callable-wrapper.md)   
 [COM Callable Wrapper](../../../docs/framework/interop/com-callable-wrapper.md)