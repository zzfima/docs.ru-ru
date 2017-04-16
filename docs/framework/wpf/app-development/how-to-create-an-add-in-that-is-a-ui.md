---
title: "Практическое руководство. Создание надстройки, являющейся пользовательским интерфейсом | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "создание надстройки, являющейся пользовательским интерфейсом [WPF]"
  - "надстройки [WPF] пользовательского интерфейса"
  - "создание надстроек пользовательского интерфейса [WPF]"
  - "Надстроек пользовательского интерфейса [WPF], создание"
  - "реализация надстроек пользовательского интерфейса [WPF]"
  - "Создание надстроек сегменты конвейера [WPF]"
ms.assetid: 86375525-282b-4039-8352-8680051a10ea
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Практическое руководство. Создание надстройки, являющейся пользовательским интерфейсом
\<?xml version="1.0" encoding="utf-8"?>
\<developerHowToDocument xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://dduestorage.blob.core.windows.net/ddueschema/developer.xsd">
  <introduction>
    <para>В этом примере показано, как создать надстройку, <token>TLA #tla_wpf</token> <token>TLA #tla_ui</token> , размещенное <token>TLA&#2;tla_wpf</token> автономное приложение.</para> 
    <para>Надстройка — это <token>TLA&#2;tla_ui</token> именно <token>TLA&#2;tla_wpf</token> пользовательского элемента управления. Содержимое пользовательского элемента управления является одна кнопка, при нажатии отображает окно сообщения. <token>TLA&#2;tla_wpf</token> автономное приложение размещает надстройки <token>TLA&#2;tla_ui</token> как содержимое главного окна приложения.</para> 
    <para> 
      <embeddedLabel>Предварительные требования</embeddedLabel>
    </para>
    <para>представлены в этом примере <token>TLA&#2;tla_wpf</token> расширения для <token>dnprdnshort</token> модель надстройки, этот сценарий, который предполагается следующее:</para>
    <list class="bullet">
      <listItem>
        <para>знания о <token>dnprdnshort</token> модель надстройки, включая конвейер, надстройку и разработку ведущего приложения. Если вы не знакомы с этими понятиями, см. раздел \<legacyLink xlink:href="8dd45b02-7218-40f9-857d-40d7b98b850b">надстройки и расширения</legacyLink>. В этом учебнике демонстрируется реализация конвейера, надстройки и ведущего приложения, в разделе \<legacyLink xlink:href="694a33c5-a040-450d-aed5-ac49fc88ce61">Пошаговое руководство: Создание расширяемого приложения</legacyLink>.</para> 
      </listItem> 
      <listItem> 
        <para>Знания о <token>TLA&#2;tla_wpf</token> расширения <token>dnprdnshort</token> модель надстроек, которые можно найти здесь: \<link xlink:href="00b4c776-29a8-4dba-b603-280a0cdc2ade">Обзор надстройки WPF</link>.</para> 
      </listItem> 
    </list> 
  </introduction> 
  <codeExample> 
    <legacy> 
      <content> 
        <para>Для создания надстройки, <token>TLA&#2;tla_wpf</token> <token>TLA&#2;tla_ui</token> требуется специальный код для каждого сегмента конвейера, надстройки и ведущего приложения.</para> 
        <para> 
          <token>autoOutline</token>
        </para>
      </content>
      <sections>
        <section address="Contract">
          <title>Реализация сегмента конвейера контракта</title>
          <content>
            <para>надстройки при <token>TLA&#2;tla_ui</token>, контракт для надстройки должен реализовать <codeEntityReference autoUpgrade="true">T:System.AddIn.Contract.INativeHandleContract</codeEntityReference>. В примере <codeInline>IWPFAddInContract</codeInline> реализует <codeEntityReference autoUpgrade="true">T:System.AddIn.Contract.INativeHandleContract</codeEntityReference>, как показано в следующем коде.</para>
            <code language="c#">using System.AddIn.Contract; // INativeHandleContract
using System.AddIn.Pipeline; // AddInContractAttribute

namespace Contracts
{
    /// &lt;summary&gt;
    /// Defines the services that an add-in will provide to a host application.
    /// In this case, the add-in is a UI.
    /// &lt;/summary&gt;
    [AddInContract]
    public interface IWPFAddInContract : INativeHandleContract {}
}</code>
          <code language="vb">Imports System.AddIn.Contract ' INativeHandleContract
Imports System.AddIn.Pipeline ' AddInContractAttribute

Namespace Contracts
    ''' &lt;summary&gt;
    ''' Defines the services that an add-in will provide to a host application.
    ''' In this case, the add-in is a UI.
    ''' &lt;/summary&gt;
    &lt;AddInContract&gt;
    Public Interface IWPFAddInContract
        Inherits INativeHandleContract
        Inherits IContract
    End Interface
End Namespace</code></content>
        </section>
        <section address="AddInViewPipeline">
          <title>Реализация сегмента конвейера надстройки представление</title>
          <content>
            <para>надстройка реализована как подкласс <codeEntityReference autoUpgrade="true">T:System.Windows.FrameworkElement</codeEntityReference> тип, представление надстройки также должно быть подклассом <codeEntityReference autoUpgrade="true">T:System.Windows.FrameworkElement</codeEntityReference>. В следующем коде показано представление надстройки контракта, реализованное как <codeInline>WPFAddInView</codeInline> класса</para> 
            <code language="c#">using System.AddIn.Pipeline; // AddInBaseAttribute
using System.Windows.Controls; // UserControl

namespace AddInViews
{
    /// &lt;summary&gt;
    /// Defines the add-in's view of the contract.
    /// &lt;/summary&gt;
    [AddInBase]
    public class WPFAddInView : UserControl { }
}</code> 
          <code language="vb">Imports System.AddIn.Pipeline ' AddInBaseAttribute
Imports System.Windows.Controls ' UserControl

Namespace AddInViews
    ''' &lt;summary&gt;
    ''' Defines the add-in's view of the contract.
    ''' &lt;/summary&gt;
    &lt;AddInBase&gt;
    Public Class WPFAddInView
        Inherits UserControl
    End Class
End Namespace</code> 
            <para>Здесь, представление надстройки является производным от <codeEntityReference autoUpgrade="true">T:System.Windows.Controls.UserControl</codeEntityReference>. Следовательно, надстройка <token>TLA&#2;tla_ui</token> также должен быть производным от <codeEntityReference autoUpgrade="true">T:System.Windows.Controls.UserControl</codeEntityReference>.</para>
          </content>
        </section>
        <section address="AddInSideAdapter">
          <title>Реализация сегмента конвейера адаптера Add-In-Side</title>
          <content>
            <para>контракт представляет <codeEntityReference autoUpgrade="true">T:System.AddIn.Contract.INativeHandleContract</codeEntityReference>, надстройка — это <codeEntityReference autoUpgrade="true">T:System.Windows.FrameworkElement</codeEntityReference> (как указано в сегмент представления надстройки конвейера). Таким образом <codeEntityReference autoUpgrade="true">T:System.Windows.FrameworkElement</codeEntityReference> должны быть преобразованы в <codeEntityReference autoUpgrade="true">T:System.AddIn.Contract.INativeHandleContract</codeEntityReference> перед пересечением границы изоляции. Эту работу выполняет, адаптер на стороне надстройки путем вызова <codeEntityReference autoUpgrade="true">M:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter(System.Windows.FrameworkElement)</codeEntityReference>, как показано в следующем коде.</para> 
            <code language="c#">using System; // IntPtr
using System.AddIn.Contract; // INativeHandleContract
using System.AddIn.Pipeline; // AddInAdapterAttribute, FrameworkElementAdapters, ContractBase
using System.Security.Permissions;

using AddInViews; // WPFAddInView
using Contracts; // IWPFAddInContract

namespace AddInSideAdapters
{
    /// &lt;summary&gt;
    /// Adapts the add-in's view of the contract to the add-in contract
    /// &lt;/summary&gt;
    [AddInAdapter]
    public class WPFAddIn_ViewToContractAddInSideAdapter : ContractBase, IWPFAddInContract
    {
        WPFAddInView wpfAddInView;

        public WPFAddIn_ViewToContractAddInSideAdapter(WPFAddInView wpfAddInView)
        {
            // Adapt the add-in view of the contract (WPFAddInView) 
            // to the contract (IWPFAddInContract)
            this.wpfAddInView = wpfAddInView;
        }

        /// &lt;summary&gt;
        /// ContractBase.QueryContract must be overridden to:
        /// * Safely return a window handle for an add-in UI to the host 
        ///   application's application.
        /// * Enable tabbing between host application UI and add-in UI, in the
        ///   "add-in is a UI" scenario.
        /// &lt;/summary&gt;
        public override IContract QueryContract(string contractIdentifier)
        {
            if (contractIdentifier.Equals(typeof(INativeHandleContract).AssemblyQualifiedName))
            {
                return FrameworkElementAdapters.ViewToContractAdapter(this.wpfAddInView);
            }

            return base.QueryContract(contractIdentifier);
        }

        /// &lt;summary&gt;
        /// GetHandle is called by the WPF add-in model from the host application's 
        /// application domain to to get the window handle for an add-in UI from the 
        /// add-in's application domain. GetHandle is called if a window handle isn't 
        /// returned by other means ie overriding ContractBase.QueryContract, 
        /// as shown above.
        /// NOTE: This method requires UnmanagedCodePermission to be called 
        ///       (full-trust by default), to prevent illegal window handle
        ///       access in partially trusted scenarios. If the add-in could
        ///       run in a partially trusted application domain 
        ///       (eg AddInSecurityLevel.Internet), you can safely return a window
        ///       handle by overriding ContractBase.QueryContract, as shown above.
        /// &lt;/summary&gt;
        [SecurityPermissionAttribute(SecurityAction.Demand, Flags = SecurityPermissionFlag.UnmanagedCode)]
        public IntPtr GetHandle()
        {
            return FrameworkElementAdapters.ViewToContractAdapter(this.wpfAddInView).GetHandle();
        }
    }
}</code> 
          <code language="vb">Imports System ' IntPtr
Imports System.AddIn.Contract ' INativeHandleContract
Imports System.AddIn.Pipeline ' AddInAdapterAttribute, FrameworkElementAdapters, ContractBase
Imports System.Security.Permissions

Imports AddInViews ' WPFAddInView
Imports Contracts ' IWPFAddInContract

Namespace AddInSideAdapters
    ''' &lt;summary&gt;
    ''' Adapts the add-in's view of the contract to the add-in contract
    ''' &lt;/summary&gt;
    &lt;AddInAdapter&gt;
    Public Class WPFAddIn_ViewToContractAddInSideAdapter
        Inherits ContractBase
        Implements IWPFAddInContract

        Private wpfAddInView As WPFAddInView

        Public Sub New(ByVal wpfAddInView As WPFAddInView)
            ' Adapt the add-in view of the contract (WPFAddInView) 
            ' to the contract (IWPFAddInContract)
            Me.wpfAddInView = wpfAddInView
        End Sub

        ''' &lt;summary&gt;
        ''' ContractBase.QueryContract must be overridden to:
        ''' * Safely return a window handle for an add-in UI to the host 
        '''   application's application.
        ''' * Enable tabbing between host application UI and add-in UI, in the
        '''   "add-in is a UI" scenario.
        ''' &lt;/summary&gt;
        Public Overrides Function QueryContract(ByVal contractIdentifier As String) As IContract
            If contractIdentifier.Equals(GetType(INativeHandleContract).AssemblyQualifiedName) Then
                Return FrameworkElementAdapters.ViewToContractAdapter(Me.wpfAddInView)
            End If

            Return MyBase.QueryContract(contractIdentifier)
        End Function

        ''' &lt;summary&gt;
        ''' GetHandle is called by the WPF add-in model from the host application's 
        ''' application domain to to get the window handle for an add-in UI from the 
        ''' add-in's application domain. GetHandle is called if a window handle isn't 
        ''' returned by other means ie overriding ContractBase.QueryContract, 
        ''' as shown above.
        ''' NOTE: This method requires UnmanagedCodePermission to be called 
        '''       (full-trust by default), to prevent illegal window handle
        '''       access in partially trusted scenarios. If the add-in could
        '''       run in a partially trusted application domain 
        '''       (eg AddInSecurityLevel.Internet), you can safely return a window
        '''       handle by overriding ContractBase.QueryContract, as shown above.
        ''' &lt;/summary&gt;
        &lt;SecurityPermissionAttribute(SecurityAction.Demand, Flags:=SecurityPermissionFlag.UnmanagedCode)&gt;
        Public Function GetHandle() As IntPtr Implements INativeHandleContract.GetHandle
            Return FrameworkElementAdapters.ViewToContractAdapter(Me.wpfAddInView).GetHandle()
        End Function

    End Class
End Namespace</code> 
            <para>В модель надстройки, где надстройка возвращает <token>TLA&#2;tla_ui</token> (см. \<link xlink:href="57f274b7-4c66-4b72-92eb-81939a393776">как: создание надстройки, возвращает пользовательский Интерфейс</link>), адаптер надстройки преобразовать <codeEntityReference autoUpgrade="true">T:System.Windows.FrameworkElement</codeEntityReference> для <codeEntityReference autoUpgrade="true">T:System.AddIn.Contract.INativeHandleContract</codeEntityReference> путем вызова <codeEntityReference autoUpgrade="true">M:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter(System.Windows.FrameworkElement)</codeEntityReference>. <codeEntityReference autoUpgrade="true">M:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter(System.Windows.FrameworkElement)</codeEntityReference> также необходимо вызвать в этой модели, несмотря на то, что вам нужно реализовать метод, с которых можно написать код, который будет вызывать его. Это делается путем переопределения <codeEntityReference autoUpgrade="true">M:System.AddIn.Pipeline.ContractBase.QueryContract(System.String)</codeEntityReference> и реализация кода, который вызывает <codeEntityReference autoUpgrade="true">M:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter(System.Windows.FrameworkElement)</codeEntityReference> Если код, вызывающий <codeEntityReference autoUpgrade="true">M:System.AddIn.Pipeline.ContractBase.QueryContract(System.String)</codeEntityReference> ожидает <codeEntityReference autoUpgrade="true">T:System.AddIn.Contract.INativeHandleContract</codeEntityReference>. В этом случае вызывающий объект будет адаптер на стороне узла, который рассматривается в следующем подразделе.</para>
            <alert class="note">
              <para> Необходимо переопределить <codeEntityReference autoUpgrade="true">M:System.AddIn.Pipeline.ContractBase.QueryContract(System.String)</codeEntityReference> в этой модели, чтобы разрешить переходы между ведущим приложением <token>TLA&#2;tla_ui</token> и добавьте в <token>TLA&#2;tla_ui</token>. Дополнительные сведения см. в разделе «WPF надстройки ограничения» в \<link xlink:href="00b4c776-29a8-4dba-b603-280a0cdc2ade">Обзор надстройки WPF</link>.</para> 
            </alert> 
            <para>, Так как адаптер со стороны надстройки реализует интерфейс, который является производным от <codeEntityReference autoUpgrade="true">T:System.AddIn.Contract.INativeHandleContract</codeEntityReference>, необходимо также реализовать <codeEntityReference autoUpgrade="true">M:System.AddIn.Contract.INativeHandleContract.GetHandle</codeEntityReference>, несмотря на то, что этот параметр учитывается при <codeEntityReference autoUpgrade="true">M:System.AddIn.Pipeline.ContractBase.QueryContract(System.String)</codeEntityReference> переопределяется.</para>
          </content>
        </section>
        <section address="HostViewPipeline">
          <title>Реализация сегмента конвейера представление узла</title>
          <content>
            <para>в этой модели ведущее приложение обычно ожидает, что хост-представление, быть <codeEntityReference autoUpgrade="true">T:System.Windows.FrameworkElement</codeEntityReference> подкласс. Адаптер на стороне узла должен преобразовать <codeEntityReference autoUpgrade="true">T:System.AddIn.Contract.INativeHandleContract</codeEntityReference> для <codeEntityReference autoUpgrade="true">T:System.Windows.FrameworkElement</codeEntityReference> после <codeEntityReference autoUpgrade="true">T:System.AddIn.Contract.INativeHandleContract</codeEntityReference> пересекает границу изоляции. Поскольку метод не вызывается ведущим приложением для получения <codeEntityReference autoUpgrade="true">T:System.Windows.FrameworkElement</codeEntityReference>, хост-представление должно «return» <codeEntityReference autoUpgrade="true">T:System.Windows.FrameworkElement</codeEntityReference> , включая его. Следовательно, хост-представление должно быть производным от подкласс <codeEntityReference autoUpgrade="true">T:System.Windows.FrameworkElement</codeEntityReference> , могут содержать другие <token>TLA&#2;tla_ui #plural</token>, такие как <codeEntityReference autoUpgrade="true">T:System.Windows.Controls.UserControl</codeEntityReference>. В следующем коде показано хост-представление контракта, реализованное как <codeInline>WPFAddInHostView</codeInline> класса.</para>
            <code language="c#">using System.Windows.Controls; // UserControl

namespace HostViews
{
    /// &lt;summary&gt;
    /// Defines the host's view of the add-in
    /// &lt;/summary&gt;
    public class WPFAddInHostView : UserControl { }
}</code>
          <code language="vb">Imports System.Windows.Controls ' UserControl

Namespace HostViews
    ''' &lt;summary&gt;
    ''' Defines the host's view of the add-in
    ''' &lt;/summary&gt;
    Public Class WPFAddInHostView
        Inherits UserControl
    End Class
End Namespace</code>
          </content>
        </section>
        <section address="HostSideAdapter">
          <title>Реализация сегмента конвейера ведущий адаптер</title>
          <content>
            <para>контракт представляет <codeEntityReference autoUpgrade="true">T:System.AddIn.Contract.INativeHandleContract</codeEntityReference>, а ведущее приложение ожидает <codeEntityReference autoUpgrade="true">T:System.Windows.Controls.UserControl</codeEntityReference> (как указано представлением узла). Следовательно <codeEntityReference autoUpgrade="true">T:System.AddIn.Contract.INativeHandleContract</codeEntityReference> должны быть преобразованы в <codeEntityReference autoUpgrade="true">T:System.Windows.FrameworkElement</codeEntityReference> после пересечения границы изоляции перед заданием в качестве содержимого хост-представления (который является производным от <codeEntityReference autoUpgrade="true">T:System.Windows.Controls.UserControl</codeEntityReference>).</para> 
            <para>Эту работу выполняет адаптером стороне главного приложения, как показано в следующем коде. </para> 
            <code language="c#">using System.AddIn.Contract; // INativeHandleContract
using System.AddIn.Pipeline; // HostAdapterAttribute, FrameworkElementAdapters, ContractHandle
using System.Windows; // FrameworkElement

using Contracts; // IWPFAddInContract
using HostViews; // WPFAddInHostView

namespace HostSideAdapters
{
    /// &lt;summary&gt;
    /// Adapts the add-in contract to the host's view of the add-in
    /// &lt;/summary&gt;
    [HostAdapter]
    public class WPFAddIn_ContractToViewHostSideAdapter : WPFAddInHostView
    {
        IWPFAddInContract wpfAddInContract;
        ContractHandle wpfAddInContractHandle;

        public WPFAddIn_ContractToViewHostSideAdapter(IWPFAddInContract wpfAddInContract)
        {
            // Adapt the contract (IWPFAddInContract) to the host application's
            // view of the contract (WPFAddInHostView)
            this.wpfAddInContract = wpfAddInContract;

            // Prevent the reference to the contract from being released while the
            // host application uses the add-in
            this.wpfAddInContractHandle = new ContractHandle(wpfAddInContract);

            // Convert the INativeHandleContract for the add-in UI that was passed 
            // from the add-in side of the isolation boundary to a FrameworkElement
            string aqn = typeof(INativeHandleContract).AssemblyQualifiedName;
            INativeHandleContract inhc = (INativeHandleContract)wpfAddInContract.QueryContract(aqn);
            FrameworkElement fe = (FrameworkElement)FrameworkElementAdapters.ContractToViewAdapter(inhc);

            // Add FrameworkElement (which displays the UI provided by the add-in) as
            // content of the view (a UserControl)
            this.Content = fe;
        }
    }
}</code> 
          <code language="vb">Imports System.AddIn.Contract ' INativeHandleContract
Imports System.AddIn.Pipeline ' HostAdapterAttribute, FrameworkElementAdapters, ContractHandle
Imports System.Windows ' FrameworkElement

Imports Contracts ' IWPFAddInContract
Imports HostViews ' WPFAddInHostView

Namespace HostSideAdapters
    ''' &lt;summary&gt;
    ''' Adapts the add-in contract to the host's view of the add-in
    ''' &lt;/summary&gt;
    &lt;HostAdapter&gt;
    Public Class WPFAddIn_ContractToViewHostSideAdapter
        Inherits WPFAddInHostView
        Private wpfAddInContract As IWPFAddInContract
        Private wpfAddInContractHandle As ContractHandle

        Public Sub New(ByVal wpfAddInContract As IWPFAddInContract)
            ' Adapt the contract (IWPFAddInContract) to the host application's
            ' view of the contract (WPFAddInHostView)
            Me.wpfAddInContract = wpfAddInContract

            ' Prevent the reference to the contract from being released while the
            ' host application uses the add-in
            Me.wpfAddInContractHandle = New ContractHandle(wpfAddInContract)

            ' Convert the INativeHandleContract for the add-in UI that was passed 
            ' from the add-in side of the isolation boundary to a FrameworkElement
            Dim aqn As String = GetType(INativeHandleContract).AssemblyQualifiedName
            Dim inhc As INativeHandleContract = CType(wpfAddInContract.QueryContract(aqn), INativeHandleContract)
            Dim fe As FrameworkElement = CType(FrameworkElementAdapters.ContractToViewAdapter(inhc), FrameworkElement)

            ' Add FrameworkElement (which displays the UI provided by the add-in) as
            ' content of the view (a UserControl)
            Me.Content = fe
        End Sub
    End Class
End Namespace</code> 
            <para>Как можно видеть, адаптер получает <codeEntityReference autoUpgrade="true">T:System.AddIn.Contract.INativeHandleContract</codeEntityReference> путем вызова адаптер на стороне надстройки <codeEntityReference autoUpgrade="true">M:System.AddIn.Pipeline.ContractBase.QueryContract(System.String)</codeEntityReference> метод (точка, где <codeEntityReference autoUpgrade="true">T:System.AddIn.Contract.INativeHandleContract</codeEntityReference> пересекает границу изоляции).</para> 
            <para>Адаптер на стороне узла затем преобразует <codeEntityReference autoUpgrade="true">T:System.AddIn.Contract.INativeHandleContract</codeEntityReference> для <codeEntityReference autoUpgrade="true">T:System.Windows.FrameworkElement</codeEntityReference> путем вызова <codeEntityReference autoUpgrade="true">M:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter(System.AddIn.Contract.INativeHandleContract)</codeEntityReference>. Наконец <codeEntityReference autoUpgrade="true">T:System.Windows.FrameworkElement</codeEntityReference> задается как содержимое хост-представления.</para>
          </content>
        </section>
        <section address="AddIn">
          <title>Реализация надстройки</title>
          <content>
            <para>адаптер на стороне надстройки и представления надстройки в месте, надстройки можно реализовать путем наследования от представления надстройки, как показано в следующем коде.</para> 
            <code language="xaml">&lt;addInViews:WPFAddInView
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:addInViews="clr-namespace:AddInViews;assembly=AddInViews"
    x:Class="WPFAddIn1.AddInUI"&gt;

    &lt;Grid&gt;
        &lt;Button Click="clickMeButton_Click" Content="Click Me!" /&gt;        
    &lt;/Grid&gt;

&lt;/addInViews:WPFAddInView&gt;</code> 
            <code language="c#">using System.AddIn; // AddInAttribute
using System.Windows; // MessageBox, RoutedEventArgs

using AddInViews; // WPFAddInView

namespace WPFAddIn1
{
    /// &lt;summary&gt;
    /// Implements the add-in by deriving from WPFAddInView
    /// &lt;/summary&gt;
    [AddIn("WPF Add-In 1")]
    public partial class AddInUI : WPFAddInView
    {
        public AddInUI()
        {
            InitializeComponent();
        }

        void clickMeButton_Click(object sender, RoutedEventArgs e)
        {
            MessageBox.Show("Hello from WPFAddIn1");
        }
    }
}</code> 
          <code language="vb">Imports System.AddIn ' AddInAttribute
Imports System.Windows ' MessageBox, RoutedEventArgs

Imports AddInViews ' WPFAddInView

Namespace WPFAddIn1
    ''' &lt;summary&gt;
    ''' Implements the add-in by deriving from WPFAddInView
    ''' &lt;/summary&gt;
    &lt;AddIn("WPF Add-In 1")&gt;
    Partial Public Class AddInUI
        Inherits WPFAddInView
        Public Sub New()
            InitializeComponent()
        End Sub

        Private Sub clickMeButton_Click(ByVal sender As Object, ByVal e As RoutedEventArgs)
            MessageBox.Show("Hello from WPFAddIn1")
        End Sub
    End Class
End Namespace</code> 
            <para>Из этого примера можно увидеть одно любопытное преимущество данной модели: разработчикам необходимо только реализовать надстройку (поскольку это <token>TLA&#2;tla_ui</token> также), а не класс надстройки и надстройка <token>TLA&#2;tla_ui</token>.</para>
          </content>
        </section>
        <section address="HostApp">
          <title>Реализация ведущего приложения</title>
          <content>
            <para>адаптер на стороне узла и созданного представления узла, ведущее приложение может использовать <token>dnprdnshort</token> добавить в модель, чтобы открыть конвейер и получить хост-представление надстройки. В следующем коде показаны следующие действия. </para> 
            <code language="c#">// Get add-in pipeline folder (the folder in which this application was launched from)
string appPath = Environment.CurrentDirectory;

// Rebuild visual add-in pipeline
string[] warnings = AddInStore.Rebuild(appPath);
if (warnings.Length &gt; 0)
{
    string msg = "Could not rebuild pipeline:";
    foreach (string warning in warnings) msg += "\n" + warning;
    MessageBox.Show(msg);
    return;
}

// Activate add-in with Internet zone security isolation
Collection&lt;AddInToken&gt; addInTokens = AddInStore.FindAddIns(typeof(WPFAddInHostView), appPath);
AddInToken wpfAddInToken = addInTokens[0];
this.wpfAddInHostView = wpfAddInToken.Activate&lt;WPFAddInHostView&gt;(AddInSecurityLevel.Internet);

// Display add-in UI
this.addInUIHostGrid.Children.Add(this.wpfAddInHostView);</code> 
          <code language="vb">' Get add-in pipeline folder (the folder in which this application was launched from)
Dim appPath As String = Environment.CurrentDirectory

' Rebuild visual add-in pipeline
Dim warnings() As String = AddInStore.Rebuild(appPath)
If warnings.Length &gt; 0 Then
    Dim msg As String = "Could not rebuild pipeline:"
    For Each warning As String In warnings
        msg &amp;= vbLf &amp; warning
    Next warning
    MessageBox.Show(msg)
    Return
End If

' Activate add-in with Internet zone security isolation
Dim addInTokens As Collection(Of AddInToken) = AddInStore.FindAddIns(GetType(WPFAddInHostView), appPath)
Dim wpfAddInToken As AddInToken = addInTokens(0)
Me.wpfAddInHostView = wpfAddInToken.Activate(Of WPFAddInHostView)(AddInSecurityLevel.Internet)

' Display add-in UI
Me.addInUIHostGrid.Children.Add(Me.wpfAddInHostView)</code> 
            <para>Ведущее приложение использует обычный <token>dnprdnshort</token> модель надстройки код, чтобы активировать надстройки, которая неявным образом возвращает хост-представление ведущему приложению. Ведущее приложение затем отображает хост-представление (который является <codeEntityReference autoUpgrade="true">T:System.Windows.Controls.UserControl</codeEntityReference>) из <codeEntityReference autoUpgrade="true">T:System.Windows.Controls.Grid</codeEntityReference>.</para> 
            <para>Код для обработки взаимодействия с надстройкой <token>TLA&#2;tla_ui</token> работает в домен приложения надстройки. Это взаимодействие включает следующее:</para>
            <list class="bullet">
              <listItem>
                <para>обработка <codeEntityReference autoUpgrade="true">T:System.Windows.Controls.Button</codeEntityReference> <codeEntityReference autoUpgrade="true">E:System.Windows.Controls.Primitives.ButtonBase.Click</codeEntityReference> событий.</para> 
              </listItem> 
              <listItem> 
                <para>Отображение <codeEntityReference autoUpgrade="true">T:System.Windows.MessageBox</codeEntityReference>.</para> 
              </listItem> 
            </list> 
            <para>Это действие полностью изолирован от ведущего приложения.</para>
          </content>
        </section>
      </sections>
    </legacy>
  </codeExample>
  <relatedTopics>
\<legacyLink xlink:href="8dd45b02-7218-40f9-857d-40d7b98b850b">Надстройки и расширения</legacyLink>
\<link xlink:href="00b4c776-29a8-4dba-b603-280a0cdc2ade">Общие сведения о надстройках WPF</link>
</relatedTopics>
</developerHowToDocument>
