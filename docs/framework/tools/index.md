---
title: Инструменты .NET Framework
ms.date: 03/30/2017
helpviewer_keywords:
- command line, .NET Framework tools
- .NET Framework, tools
- tools [.NET Framework]
- running .NET Framework tools
ms.assetid: a2ca532d-91f7-426a-9303-417c2ee1247c
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4034a23b076bc0f3041f09dc4756646a926d6915
ms.sourcegitcommit: c217b067985905cb21eafc5dd9a83568d7ff4e45
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/22/2018
ms.locfileid: "36314689"
---
# <a name="net-framework-tools"></a>Инструменты .NET Framework
Назначение средств .NET Framework состоит в том, чтобы облегчить создание, развертывание и администрирование приложений и компонентов, предназначенных для .NET Framework.  
  
Большинство инструментов .NET Framework, описание которых дано в этом разделе, устанавливаются автоматически вместе с Visual Studio. Скачать Visual Studio можно на странице [Скачиваемых файлов Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017).
  
 Все программы, за исключением средства просмотра кэша сборок (Shfusion.dll), запускаются из командной строки. Доступ к библиотеке "Shfusion.dll" осуществляется из проводника.  
  
 Для запуска этих программ командной строки рекомендуется использовать командную строку разработчика для Visual Studio. Эти служебные программы позволяют запустить средства легко, без перемещения в папку установки. Дополнительные сведения см. в разделе [Командные строки](../../../docs/framework/tools/developer-command-prompt-for-vs.md).  
  
> [!NOTE]
>  Некоторые средства относятся либо к 32-разрядным компьютерам, либо к 64-разрядным компьютерам. Обязательно проверьте, подходит ли запускаемая версия программы для локального компьютера.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Al.exe (компоновщик сборок)](../../../docs/framework/tools/al-exe-assembly-linker.md)  
 Создает файл, обладающий манифестом сборки из модулей или файлов ресурсов.  
  
 [Aximp.exe (программа импорта элементов ActiveX форм Windows Forms)](../../../docs/framework/tools/aximp-exe-windows-forms-activex-control-importer.md)  
 Преобразует определения типов для элемента управления ActiveX из библиотеки типов COM в элемент управления Windows Forms.  
  
 [Caspol.exe (средство настройки политики управления доступом для кода)](../../../docs/framework/tools/caspol-exe-code-access-security-policy-tool.md)  
 Позволяют просматривать и настраивать политику безопасности на уровне политики компьютера, пользователя и предприятия. В [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] и более поздних версиях эта программа не влияет на политику разграничения доступа кода, если только для элемента [\<legacyCasPolicy>](../../../docs/framework/configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) не задано значение `true`. Дополнительные сведения см. в разделе [Изменения системы безопасности](../../../docs/framework/security/security-changes.md).  
  
 [Cert2spc.exe (средство проверки сертификата издателя программного обеспечения)](../../../docs/framework/tools/cert2spc-exe-software-publisher-certificate-test-tool.md)  
 Создает сертификат издателя программного обеспечения (SPC) из одного или более сертификатов X.509. Этот инструмент предназначен только для тестирования.  
  
 [Certmgr.exe (средство диспетчера сертификатов)](../../../docs/framework/tools/certmgr-exe-certificate-manager-tool.md)  
 Управляет сертификатами, списками доверенных сертификатов (CTL) и списками отзыва сертификатов (CRL).  
  
 [Clrver.exe (средство проверки версий среды CLR)](../../../docs/framework/tools/clrver-exe-clr-version-tool.md)  
 Выводит отчет о всех установленных на компьютере версиях среды CLR.  
  
 [CorFlags.exe (средство преобразования CorFlags)](../../../docs/framework/tools/corflags-exe-corflags-conversion-tool.md)  
 Позволяет настраивать раздел CorFlags заголовка переносимого исполняемого (PE) образа.  
  
 [Fuslogvw.exe (средство просмотра журнала привязки сборок)](../../../docs/framework/tools/fuslogvw-exe-assembly-binding-log-viewer.md)  
 Отображает сведения о привязках сборки, помогающие определить, почему платформа .NET Framework не может найти сборку во время выполнения.  
  
 [Gacutil.exe (программа глобального кэша сборок)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)  
 Позволяет просматривать содержимое глобального кэша сборок и кэша загрузки и выполнять различные операции с этим содержимым.  
  
 [Ilasm.exe (ассемблер IL)](../../../docs/framework/tools/ilasm-exe-il-assembler.md)  
 Создает переносимый исполняемый файл (PE) из файла промежуточного языка (IL). Можно запустить полученный исполняемый файл, чтобы проверить, выполняется ли код IL так, как ожидалось.  
  
 [Ildasm.exe (дизассемблер IL)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md)  
 Принимает входной исполняемый файл (PE), содержащий код на языке IL, и создает на его основе текстовый файл, который может быть входным для ассемблера IL (Ilasm.exe).  
  
 [Installutil.exe (инструмент для установки)](../../../docs/framework/tools/installutil-exe-installer-tool.md)  
 Позволяет устанавливать и удалять ресурсы сервера, выполняя компоненты установщика в указанной сборке. (Работает с классами в пространстве имен <xref:System.Configuration.Install>.) Позволяет устанавливать и удалять ресурсы сервера, выполняя компоненты установщика в указанной сборке. (Работает с классами в пространстве имен <xref:System.Configuration.Install>.)  
  
 [Lc.exe (компилятор лицензий)](../../../docs/framework/tools/lc-exe-license-compiler.md)  
 Считывает текстовые файлы, содержащие сведения о лицензиях, и создает файл .licenses, который может быть внедрен в исполняемый файл среды CLR в качестве ресурса. Считывает текстовые файлы, содержащие сведения о лицензиях, и создает файл .licenses, который может быть внедрен в исполняемый файл среды CLR в качестве ресурса.  
  
 [Mage.exe (средство создания и редактирования манифеста)](../../../docs/framework/tools/mage-exe-manifest-generation-and-editing-tool.md)  
 Позволяет создавать, редактировать и подписывать манифесты приложения и развертывания. В качестве средства командной строки программа Mage.exe может выполняться как в пакетных скриптах, так и в других Windows-приложениях, включая приложения ASP.NET.  
  
 [MageUI.exe (средство создания и редактирования манифестов, графический клиент)](../../../docs/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client.md)  
 Поддерживает те же функциональные возможности, что и средство командной строки Mage.exe, однако использует интерфейс пользователя на основе Windows. Поддерживает те же функциональные возможности, что и средство командной строки Mage.exe, однако использует интерфейс пользователя на основе Windows.  
  
 [MDbg.exe (отладчик командной строки для .NET Framework)](../../../docs/framework/tools/mdbg-exe.md)  
 Помогает разработчикам программ и приложений в поиске и исправлении ошибок в программах, работающих в общеязыковой среде выполнения .NET Framework. Этот инструмент использует отладочный API-интерфейс среды выполнения.  
  
 [Mgmtclassgen.exe (генератор строго типизированных классов управления)](../../../docs/framework/tools/mgmtclassgen-exe.md)  
 Позволяет создавать управляемый класс с ранней привязкой для заданного класса инструментария управления Windows (WMI).  
  
 [Mpgo.exe (управляемое средство профильной оптимизации)](../../../docs/framework/tools/mpgo-exe-managed-profile-guided-optimization-tool.md)  
 Позволяет настроить сборки образов в машинном коде с помощью общих пользовательских сценариев. С помощью программы Mpgo.exe можно создавать и использовать данные профилирования для сборок приложения с образами в машинном коде (не сборок .NET Framework) с помощью сценариев обучения, выбранных разработчиком приложения.  
  
 [Ngen.exe (генератор образов в машинном коде)](../../../docs/framework/tools/ngen-exe-native-image-generator.md)  
 Повышает производительность управляемых приложений за счет использования образов в машинном коде (файлов, содержащих скомпилированный для конкретного процессора машинный код). Среда выполнения может использовать образы в машинном коде, находящиеся в кэше, вместо использования JIT-компилятора для компиляции исходной сборки.  
  
 [Peverify.exe (средство PEVerify)](../../../docs/framework/tools/peverify-exe-peverify-tool.md)  
 Помогает проверить, удовлетворяет ли код на языке MSIL и связанные с ним метаданные требованиям безопасности типа. Помогает проверить, удовлетворяет ли код на языке MSIL и связанные с ним метаданные требованиям безопасности типа.  
  
 [Regasm.exe (средство регистрации сборок)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md)  
 Считывает метаданные из сборки и добавляет в реестр необходимые записи. Это позволяет COM-клиентам отображаться как классы платформы .NET Framework.  
  
 [Regsvcs.exe (программа установки служб .NET)](../../../docs/framework/tools/regsvcs-exe-net-services-installation-tool.md)  
 Загружает и регистрирует сборку, создает и устанавливает библиотеку типов в заданное приложение COM+ версии 1.0, а также настраивает службы, программно добавленные вами в класс.  
  
 [Resgen.exe (генератор файлов ресурсов)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md)  
 Преобразует текстовые файлы (.txt или .restext) и файлы ресурсов на основе XML (.resx) в двоичные файлы среды CLR (.resources), которые могут быть внедрены в двоичный исполняемый файл среды выполнения или скомпилированы во вспомогательные сборки.  
  
 [SecAnnotate.exe (средство создания заметок безопасности .NET)](../../../docs/framework/tools/secannotate-exe-net-security-annotator-tool.md)  
 Идентифицирует части сборки SecurityCritical и SecuritySafeCritical. Идентифицирует части `SecurityCritical` и `SecuritySafeCritical` в сборке.  
  
 [SignTool.exe (программа подписывания)](../../../docs/framework/tools/signtool-exe.md)  
 Добавляет в файлы цифровую подпись, проверяет подписи файлов и создает отметки времени для файлов.  
  
 [Sn.exe (средство строгих имен)](../../../docs/framework/tools/sn-exe-strong-name-tool.md)  
 Позволяет создавать сборки со строгими именами. Это средство предусматривает параметры для управления ключами, генерации подписи и ее проверки.  
  
 [SOS.dll (расширение отладки SOS)](../../../docs/framework/tools/sos-dll-sos-debugging-extension.md)  
 Помогает отлаживать управляемые программы в отладчике WinDbg.exe и в Visual Studio, предоставляя информацию о внутренней среде CLR.  
  
 [SqlMetal.exe (средство создания кода)](../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)  
 Создает код и сопоставление для компонента LINQ to SQL платформы .NET Framework.  
  
 [Storeadm.exe (средство изолированного хранилища)](../../../docs/framework/tools/storeadm-exe-isolated-storage-tool.md)  
 Управляет изолированным хранилищем; предоставляет возможности для получения списка пользовательских сохранений и их удаления.  
  
 [Tlbexp.exe (программа экспорта библиотек типов)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md)  
 Создает библиотеку типов, описывающую типы, определенные в сборке среды CLR.  
  
 [Tlbimp.exe (программа экспорта библиотек типов)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md)  
 Выполняет преобразование определений типов, имеющихся в библиотеке типов COM, в эквивалентные определения сборки среды CLR.  
  
 [Winmdexp.exe (средство экспорта метаданных среды выполнения Windows)](../../../docs/framework/tools/winmdexp-exe-windows-runtime-metadata-export-tool.md)  
 Экспортирует сборку .NET Framework, скомпилированную как WINMDOBJ-файл, в компонент среды выполнения Windows, который упаковывается в WINMD-файл, содержащий и метаданные среды выполнения Windows, и информацию о реализации.  
  
 [Winres.exe (редактор ресурсов Windows Forms)](../../../docs/framework/tools/winres-exe-windows-forms-resource-editor.md)  
 Помогает производить локализацию ресурсов пользовательского интерфейса (файлы .resx или .resources), используемых формами Windows Forms. Можно перевести строки, а затем изменять размеры элементов управления, перемещать их и скрывать, чтобы вместить в них локализованные строки.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Инструменты](http://msdn.microsoft.com/library/f533241c-317c-445e-88ca-c80c8d078fca)  
 Включает такие инструменты, как средство соответствия isXPS (isXPS.exe) и средства профилирования производительности.  
  
 [Средства Windows Communication Foundation](../../../docs/framework/wcf/tools.md)  
 Включает средства, упрощающие создание, развертывание и управление приложениями Windows Communication Foundation (WCF).
