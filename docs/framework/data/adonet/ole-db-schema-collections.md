---
title: Коллекции схемы OLE DB
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: 6dc187b0a876d9e167a74f2381db156dde2764fe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61771999"
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="6165d-102">Коллекции схемы OLE DB</span><span class="sxs-lookup"><span data-stu-id="6165d-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="6165d-103">В данном разделе рассматривается поддержка коллекций схем для поставщиков OLE DB для Microsoft SQL Server, Oracle и Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="6165d-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="6165d-104">Поставщик OLE DB для Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="6165d-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="6165d-105">Драйвер Microsoft SQL Server OLE DB поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.</span><span class="sxs-lookup"><span data-stu-id="6165d-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="6165d-106">Таблицы</span><span class="sxs-lookup"><span data-stu-id="6165d-106">Tables</span></span>  
  
- <span data-ttu-id="6165d-107">Столбцы</span><span class="sxs-lookup"><span data-stu-id="6165d-107">Columns</span></span>  
  
- <span data-ttu-id="6165d-108">Процедуры</span><span class="sxs-lookup"><span data-stu-id="6165d-108">Procedures</span></span>  
  
- <span data-ttu-id="6165d-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="6165d-109">ProcedureParameters</span></span>  
  
- <span data-ttu-id="6165d-110">Catalog</span><span class="sxs-lookup"><span data-stu-id="6165d-110">Catalog</span></span>  
  
- <span data-ttu-id="6165d-111">Индексы</span><span class="sxs-lookup"><span data-stu-id="6165d-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="6165d-112">Таблицы</span><span class="sxs-lookup"><span data-stu-id="6165d-112">Tables</span></span>  
  
|<span data-ttu-id="6165d-113">ColumnName</span><span class="sxs-lookup"><span data-stu-id="6165d-113">ColumnName</span></span>|<span data-ttu-id="6165d-114">DataType</span><span class="sxs-lookup"><span data-stu-id="6165d-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="6165d-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="6165d-115">TABLE_CATALOG</span></span>|<span data-ttu-id="6165d-116">String</span><span class="sxs-lookup"><span data-stu-id="6165d-116">String</span></span>|  
|<span data-ttu-id="6165d-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="6165d-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="6165d-118">String</span><span class="sxs-lookup"><span data-stu-id="6165d-118">String</span></span>|  
|<span data-ttu-id="6165d-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="6165d-119">TABLE_NAME</span></span>|<span data-ttu-id="6165d-120">String</span><span class="sxs-lookup"><span data-stu-id="6165d-120">String</span></span>|  
|<span data-ttu-id="6165d-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="6165d-121">TABLE_TYPE</span></span>|<span data-ttu-id="6165d-122">String</span><span class="sxs-lookup"><span data-stu-id="6165d-122">String</span></span>|  
|<span data-ttu-id="6165d-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="6165d-123">TABLE_GUID</span></span>|<span data-ttu-id="6165d-124">Guid</span><span class="sxs-lookup"><span data-stu-id="6165d-124">Guid</span></span>|  
|<span data-ttu-id="6165d-125">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6165d-125">DESCRIPTION</span></span>|<span data-ttu-id="6165d-126">String</span><span class="sxs-lookup"><span data-stu-id="6165d-126">String</span></span>|  
|<span data-ttu-id="6165d-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="6165d-127">TABLE_PROPID</span></span>|<span data-ttu-id="6165d-128">Int64</span><span class="sxs-lookup"><span data-stu-id="6165d-128">Int64</span></span>|  
|<span data-ttu-id="6165d-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="6165d-129">DATE_CREATED</span></span>|<span data-ttu-id="6165d-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="6165d-130">DateTime</span></span>|  
|<span data-ttu-id="6165d-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="6165d-131">DATE_MODIFIED</span></span>|<span data-ttu-id="6165d-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="6165d-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="6165d-133">Столбцы</span><span class="sxs-lookup"><span data-stu-id="6165d-133">Columns</span></span>  
  
|<span data-ttu-id="6165d-134">ColumnName</span><span class="sxs-lookup"><span data-stu-id="6165d-134">ColumnName</span></span>|<span data-ttu-id="6165d-135">DataType</span><span class="sxs-lookup"><span data-stu-id="6165d-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="6165d-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="6165d-136">TABLE_CATALOG</span></span>|<span data-ttu-id="6165d-137">String</span><span class="sxs-lookup"><span data-stu-id="6165d-137">String</span></span>|  
|<span data-ttu-id="6165d-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="6165d-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="6165d-139">String</span><span class="sxs-lookup"><span data-stu-id="6165d-139">String</span></span>|  
|<span data-ttu-id="6165d-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="6165d-140">TABLE_NAME</span></span>|<span data-ttu-id="6165d-141">String</span><span class="sxs-lookup"><span data-stu-id="6165d-141">String</span></span>|  
|<span data-ttu-id="6165d-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="6165d-142">COLUMN_NAME</span></span>|<span data-ttu-id="6165d-143">String</span><span class="sxs-lookup"><span data-stu-id="6165d-143">String</span></span>|  
|<span data-ttu-id="6165d-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="6165d-144">COLUMN_GUID</span></span>|<span data-ttu-id="6165d-145">Guid</span><span class="sxs-lookup"><span data-stu-id="6165d-145">Guid</span></span>|  
|<span data-ttu-id="6165d-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="6165d-146">COLUMN_PROPID</span></span>|<span data-ttu-id="6165d-147">Int64</span><span class="sxs-lookup"><span data-stu-id="6165d-147">Int64</span></span>|  
|<span data-ttu-id="6165d-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="6165d-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="6165d-149">Int64</span><span class="sxs-lookup"><span data-stu-id="6165d-149">Int64</span></span>|  
|<span data-ttu-id="6165d-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="6165d-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="6165d-151">Boolean</span><span class="sxs-lookup"><span data-stu-id="6165d-151">Boolean</span></span>|  
|<span data-ttu-id="6165d-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="6165d-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="6165d-153">String</span><span class="sxs-lookup"><span data-stu-id="6165d-153">String</span></span>|  
|<span data-ttu-id="6165d-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="6165d-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="6165d-155">Int64</span><span class="sxs-lookup"><span data-stu-id="6165d-155">Int64</span></span>|  
|<span data-ttu-id="6165d-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="6165d-156">IS_NULLABLE</span></span>|<span data-ttu-id="6165d-157">Boolean</span><span class="sxs-lookup"><span data-stu-id="6165d-157">Boolean</span></span>|  
|<span data-ttu-id="6165d-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="6165d-158">DATA_TYPE</span></span>|<span data-ttu-id="6165d-159">Int32</span><span class="sxs-lookup"><span data-stu-id="6165d-159">Int32</span></span>|  
|<span data-ttu-id="6165d-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="6165d-160">TYPE_GUID</span></span>|<span data-ttu-id="6165d-161">Guid</span><span class="sxs-lookup"><span data-stu-id="6165d-161">Guid</span></span>|  
|<span data-ttu-id="6165d-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="6165d-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="6165d-163">Int64</span><span class="sxs-lookup"><span data-stu-id="6165d-163">Int64</span></span>|  
|<span data-ttu-id="6165d-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="6165d-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="6165d-165">Int64</span><span class="sxs-lookup"><span data-stu-id="6165d-165">Int64</span></span>|  
|<span data-ttu-id="6165d-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="6165d-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="6165d-167">Int32</span><span class="sxs-lookup"><span data-stu-id="6165d-167">Int32</span></span>|  
|<span data-ttu-id="6165d-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="6165d-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="6165d-169">Int16</span><span class="sxs-lookup"><span data-stu-id="6165d-169">Int16</span></span>|  
|<span data-ttu-id="6165d-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="6165d-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="6165d-171">Int64</span><span class="sxs-lookup"><span data-stu-id="6165d-171">Int64</span></span>|  
|<span data-ttu-id="6165d-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="6165d-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="6165d-173">String</span><span class="sxs-lookup"><span data-stu-id="6165d-173">String</span></span>|  
|<span data-ttu-id="6165d-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="6165d-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="6165d-175">String</span><span class="sxs-lookup"><span data-stu-id="6165d-175">String</span></span>|  
|<span data-ttu-id="6165d-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="6165d-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="6165d-177">String</span><span class="sxs-lookup"><span data-stu-id="6165d-177">String</span></span>|  
|<span data-ttu-id="6165d-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="6165d-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="6165d-179">String</span><span class="sxs-lookup"><span data-stu-id="6165d-179">String</span></span>|  
|<span data-ttu-id="6165d-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="6165d-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="6165d-181">String</span><span class="sxs-lookup"><span data-stu-id="6165d-181">String</span></span>|  
|<span data-ttu-id="6165d-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="6165d-182">COLLATION_NAME</span></span>|<span data-ttu-id="6165d-183">String</span><span class="sxs-lookup"><span data-stu-id="6165d-183">String</span></span>|  
|<span data-ttu-id="6165d-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="6165d-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="6165d-185">String</span><span class="sxs-lookup"><span data-stu-id="6165d-185">String</span></span>|  
|<span data-ttu-id="6165d-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="6165d-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="6165d-187">String</span><span class="sxs-lookup"><span data-stu-id="6165d-187">String</span></span>|  
|<span data-ttu-id="6165d-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="6165d-188">DOMAIN_NAME</span></span>|<span data-ttu-id="6165d-189">String</span><span class="sxs-lookup"><span data-stu-id="6165d-189">String</span></span>|  
|<span data-ttu-id="6165d-190">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6165d-190">DESCRIPTION</span></span>|<span data-ttu-id="6165d-191">String</span><span class="sxs-lookup"><span data-stu-id="6165d-191">String</span></span>|  
|<span data-ttu-id="6165d-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="6165d-192">COLUMN_LCID</span></span>|<span data-ttu-id="6165d-193">Int32</span><span class="sxs-lookup"><span data-stu-id="6165d-193">Int32</span></span>|  
|<span data-ttu-id="6165d-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="6165d-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="6165d-195">Int32</span><span class="sxs-lookup"><span data-stu-id="6165d-195">Int32</span></span>|  
|<span data-ttu-id="6165d-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="6165d-196">COLUMN_SORTID</span></span>|<span data-ttu-id="6165d-197">Int32</span><span class="sxs-lookup"><span data-stu-id="6165d-197">Int32</span></span>|  
|<span data-ttu-id="6165d-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="6165d-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="6165d-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="6165d-199">Byte[]</span></span>|  
|<span data-ttu-id="6165d-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="6165d-200">IS_COMPUTED</span></span>|<span data-ttu-id="6165d-201">Boolean</span><span class="sxs-lookup"><span data-stu-id="6165d-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="6165d-202">Процедуры</span><span class="sxs-lookup"><span data-stu-id="6165d-202">Procedures</span></span>  
  
|<span data-ttu-id="6165d-203">ColumnName</span><span class="sxs-lookup"><span data-stu-id="6165d-203">ColumnName</span></span>|<span data-ttu-id="6165d-204">DataType</span><span class="sxs-lookup"><span data-stu-id="6165d-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="6165d-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="6165d-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="6165d-206">String</span><span class="sxs-lookup"><span data-stu-id="6165d-206">String</span></span>|  
|<span data-ttu-id="6165d-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="6165d-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="6165d-208">String</span><span class="sxs-lookup"><span data-stu-id="6165d-208">String</span></span>|  
|<span data-ttu-id="6165d-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="6165d-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="6165d-210">String</span><span class="sxs-lookup"><span data-stu-id="6165d-210">String</span></span>|  
|<span data-ttu-id="6165d-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="6165d-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="6165d-212">Int16</span><span class="sxs-lookup"><span data-stu-id="6165d-212">Int16</span></span>|  
|<span data-ttu-id="6165d-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="6165d-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="6165d-214">String</span><span class="sxs-lookup"><span data-stu-id="6165d-214">String</span></span>|  
|<span data-ttu-id="6165d-215">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6165d-215">DESCRIPTION</span></span>|<span data-ttu-id="6165d-216">String</span><span class="sxs-lookup"><span data-stu-id="6165d-216">String</span></span>|  
|<span data-ttu-id="6165d-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="6165d-217">DATE_CREATED</span></span>|<span data-ttu-id="6165d-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="6165d-218">DateTime</span></span>|  
|<span data-ttu-id="6165d-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="6165d-219">DATE_MODIFIED</span></span>|<span data-ttu-id="6165d-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="6165d-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="6165d-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="6165d-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="6165d-222">ColumnName</span><span class="sxs-lookup"><span data-stu-id="6165d-222">ColumnName</span></span>|<span data-ttu-id="6165d-223">DataType</span><span class="sxs-lookup"><span data-stu-id="6165d-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="6165d-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="6165d-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="6165d-225">String</span><span class="sxs-lookup"><span data-stu-id="6165d-225">String</span></span>|  
|<span data-ttu-id="6165d-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="6165d-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="6165d-227">String</span><span class="sxs-lookup"><span data-stu-id="6165d-227">String</span></span>|  
|<span data-ttu-id="6165d-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="6165d-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="6165d-229">String</span><span class="sxs-lookup"><span data-stu-id="6165d-229">String</span></span>|  
|<span data-ttu-id="6165d-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="6165d-230">PARAMETER_NAME</span></span>|<span data-ttu-id="6165d-231">String</span><span class="sxs-lookup"><span data-stu-id="6165d-231">String</span></span>|  
|<span data-ttu-id="6165d-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="6165d-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="6165d-233">Int32</span><span class="sxs-lookup"><span data-stu-id="6165d-233">Int32</span></span>|  
|<span data-ttu-id="6165d-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="6165d-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="6165d-235">Int32</span><span class="sxs-lookup"><span data-stu-id="6165d-235">Int32</span></span>|  
|<span data-ttu-id="6165d-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="6165d-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="6165d-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="6165d-237">Boolean</span></span>|  
|<span data-ttu-id="6165d-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="6165d-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="6165d-239">String</span><span class="sxs-lookup"><span data-stu-id="6165d-239">String</span></span>|  
|<span data-ttu-id="6165d-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="6165d-240">IS_NULLABLE</span></span>|<span data-ttu-id="6165d-241">Boolean</span><span class="sxs-lookup"><span data-stu-id="6165d-241">Boolean</span></span>|  
|<span data-ttu-id="6165d-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="6165d-242">DATA_TYPE</span></span>|<span data-ttu-id="6165d-243">Int32</span><span class="sxs-lookup"><span data-stu-id="6165d-243">Int32</span></span>|  
|<span data-ttu-id="6165d-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="6165d-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="6165d-245">Int64</span><span class="sxs-lookup"><span data-stu-id="6165d-245">Int64</span></span>|  
|<span data-ttu-id="6165d-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="6165d-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="6165d-247">Int64</span><span class="sxs-lookup"><span data-stu-id="6165d-247">Int64</span></span>|  
|<span data-ttu-id="6165d-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="6165d-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="6165d-249">Int32</span><span class="sxs-lookup"><span data-stu-id="6165d-249">Int32</span></span>|  
|<span data-ttu-id="6165d-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="6165d-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="6165d-251">Int16</span><span class="sxs-lookup"><span data-stu-id="6165d-251">Int16</span></span>|  
|<span data-ttu-id="6165d-252">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6165d-252">DESCRIPTION</span></span>|<span data-ttu-id="6165d-253">String</span><span class="sxs-lookup"><span data-stu-id="6165d-253">String</span></span>|  
|<span data-ttu-id="6165d-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="6165d-254">TYPE_NAME</span></span>|<span data-ttu-id="6165d-255">String</span><span class="sxs-lookup"><span data-stu-id="6165d-255">String</span></span>|  
|<span data-ttu-id="6165d-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="6165d-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="6165d-257">String</span><span class="sxs-lookup"><span data-stu-id="6165d-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="6165d-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="6165d-258">Catalog</span></span>  
  
|<span data-ttu-id="6165d-259">ColumnName</span><span class="sxs-lookup"><span data-stu-id="6165d-259">ColumnName</span></span>|<span data-ttu-id="6165d-260">DataType</span><span class="sxs-lookup"><span data-stu-id="6165d-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="6165d-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="6165d-261">CATALOG_NAME</span></span>|<span data-ttu-id="6165d-262">String</span><span class="sxs-lookup"><span data-stu-id="6165d-262">String</span></span>|  
|<span data-ttu-id="6165d-263">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6165d-263">DESCRIPTION</span></span>|<span data-ttu-id="6165d-264">String</span><span class="sxs-lookup"><span data-stu-id="6165d-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="6165d-265">Индексы</span><span class="sxs-lookup"><span data-stu-id="6165d-265">Indexes</span></span>  
  
|<span data-ttu-id="6165d-266">ColumnName</span><span class="sxs-lookup"><span data-stu-id="6165d-266">ColumnName</span></span>|<span data-ttu-id="6165d-267">DataType</span><span class="sxs-lookup"><span data-stu-id="6165d-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="6165d-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="6165d-268">TABLE_CATALOG</span></span>|<span data-ttu-id="6165d-269">String</span><span class="sxs-lookup"><span data-stu-id="6165d-269">String</span></span>|  
|<span data-ttu-id="6165d-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="6165d-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="6165d-271">String</span><span class="sxs-lookup"><span data-stu-id="6165d-271">String</span></span>|  
|<span data-ttu-id="6165d-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="6165d-272">TABLE_NAME</span></span>|<span data-ttu-id="6165d-273">String</span><span class="sxs-lookup"><span data-stu-id="6165d-273">String</span></span>|  
|<span data-ttu-id="6165d-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="6165d-274">INDEX_CATALOG</span></span>|<span data-ttu-id="6165d-275">String</span><span class="sxs-lookup"><span data-stu-id="6165d-275">String</span></span>|  
|<span data-ttu-id="6165d-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="6165d-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="6165d-277">String</span><span class="sxs-lookup"><span data-stu-id="6165d-277">String</span></span>|  
|<span data-ttu-id="6165d-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="6165d-278">INDEX_NAME</span></span>|<span data-ttu-id="6165d-279">String</span><span class="sxs-lookup"><span data-stu-id="6165d-279">String</span></span>|  
|<span data-ttu-id="6165d-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="6165d-280">PRIMARY_KEY</span></span>|<span data-ttu-id="6165d-281">Boolean</span><span class="sxs-lookup"><span data-stu-id="6165d-281">Boolean</span></span>|  
|<span data-ttu-id="6165d-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="6165d-282">UNIQUE</span></span>|<span data-ttu-id="6165d-283">Boolean</span><span class="sxs-lookup"><span data-stu-id="6165d-283">Boolean</span></span>|  
|<span data-ttu-id="6165d-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="6165d-284">CLUSTERED</span></span>|<span data-ttu-id="6165d-285">Boolean</span><span class="sxs-lookup"><span data-stu-id="6165d-285">Boolean</span></span>|  
|<span data-ttu-id="6165d-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="6165d-286">TYPE</span></span>|<span data-ttu-id="6165d-287">Int32</span><span class="sxs-lookup"><span data-stu-id="6165d-287">Int32</span></span>|  
|<span data-ttu-id="6165d-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="6165d-288">FILL_FACTOR</span></span>|<span data-ttu-id="6165d-289">Int32</span><span class="sxs-lookup"><span data-stu-id="6165d-289">Int32</span></span>|  
|<span data-ttu-id="6165d-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="6165d-290">INITIAL_SIZE</span></span>|<span data-ttu-id="6165d-291">Int32</span><span class="sxs-lookup"><span data-stu-id="6165d-291">Int32</span></span>|  
|<span data-ttu-id="6165d-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="6165d-292">NULLS</span></span>|<span data-ttu-id="6165d-293">Int32</span><span class="sxs-lookup"><span data-stu-id="6165d-293">Int32</span></span>|  
|<span data-ttu-id="6165d-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="6165d-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="6165d-295">Boolean</span><span class="sxs-lookup"><span data-stu-id="6165d-295">Boolean</span></span>|  
|<span data-ttu-id="6165d-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="6165d-296">AUTO_UPDATE</span></span>|<span data-ttu-id="6165d-297">Boolean</span><span class="sxs-lookup"><span data-stu-id="6165d-297">Boolean</span></span>|  
|<span data-ttu-id="6165d-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="6165d-298">NULL_COLLATION</span></span>|<span data-ttu-id="6165d-299">Int32</span><span class="sxs-lookup"><span data-stu-id="6165d-299">Int32</span></span>|  
|<span data-ttu-id="6165d-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="6165d-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="6165d-301">Int64</span><span class="sxs-lookup"><span data-stu-id="6165d-301">Int64</span></span>|  
|<span data-ttu-id="6165d-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="6165d-302">COLUMN_NAME</span></span>|<span data-ttu-id="6165d-303">String</span><span class="sxs-lookup"><span data-stu-id="6165d-303">String</span></span>|  
|<span data-ttu-id="6165d-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="6165d-304">COLUMN_GUID</span></span>|<span data-ttu-id="6165d-305">Guid</span><span class="sxs-lookup"><span data-stu-id="6165d-305">Guid</span></span>|  
|<span data-ttu-id="6165d-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="6165d-306">COLUMN_PROPID</span></span>|<span data-ttu-id="6165d-307">Int64</span><span class="sxs-lookup"><span data-stu-id="6165d-307">Int64</span></span>|  
|<span data-ttu-id="6165d-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="6165d-308">COLLATION</span></span>|<span data-ttu-id="6165d-309">Int16</span><span class="sxs-lookup"><span data-stu-id="6165d-309">Int16</span></span>|  
|<span data-ttu-id="6165d-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="6165d-310">CARDINALITY</span></span>|<span data-ttu-id="6165d-311">Десятичное число</span><span class="sxs-lookup"><span data-stu-id="6165d-311">Decimal</span></span>|  
|<span data-ttu-id="6165d-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="6165d-312">PAGES</span></span>|<span data-ttu-id="6165d-313">Int32</span><span class="sxs-lookup"><span data-stu-id="6165d-313">Int32</span></span>|  
|<span data-ttu-id="6165d-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="6165d-314">FILTER_CONDITION</span></span>|<span data-ttu-id="6165d-315">String</span><span class="sxs-lookup"><span data-stu-id="6165d-315">String</span></span>|  
|<span data-ttu-id="6165d-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="6165d-316">INTEGRATED</span></span>|<span data-ttu-id="6165d-317">Boolean</span><span class="sxs-lookup"><span data-stu-id="6165d-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="6165d-318">Поставщик Microsoft OLE DB для Oracle</span><span class="sxs-lookup"><span data-stu-id="6165d-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="6165d-319">Драйвер OLE DB для Oracle (Майкрософт) поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.</span><span class="sxs-lookup"><span data-stu-id="6165d-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="6165d-320">Таблицы</span><span class="sxs-lookup"><span data-stu-id="6165d-320">Tables</span></span>  
  
- <span data-ttu-id="6165d-321">Столбцы</span><span class="sxs-lookup"><span data-stu-id="6165d-321">Columns</span></span>  
  
- <span data-ttu-id="6165d-322">Процедуры</span><span class="sxs-lookup"><span data-stu-id="6165d-322">Procedures</span></span>  
  
- <span data-ttu-id="6165d-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="6165d-323">ProcedureColumns</span></span>  
  
- <span data-ttu-id="6165d-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="6165d-324">ProcedureParameters</span></span>  
  
- <span data-ttu-id="6165d-325">Представления</span><span class="sxs-lookup"><span data-stu-id="6165d-325">Views</span></span>  
  
- <span data-ttu-id="6165d-326">Индексы</span><span class="sxs-lookup"><span data-stu-id="6165d-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="6165d-327">Таблицы</span><span class="sxs-lookup"><span data-stu-id="6165d-327">Tables</span></span>  
  
|<span data-ttu-id="6165d-328">ColumnName</span><span class="sxs-lookup"><span data-stu-id="6165d-328">ColumnName</span></span>|<span data-ttu-id="6165d-329">DataType</span><span class="sxs-lookup"><span data-stu-id="6165d-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="6165d-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="6165d-330">TABLE_CATALOG</span></span>|<span data-ttu-id="6165d-331">String</span><span class="sxs-lookup"><span data-stu-id="6165d-331">String</span></span>|  
|<span data-ttu-id="6165d-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="6165d-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="6165d-333">String</span><span class="sxs-lookup"><span data-stu-id="6165d-333">String</span></span>|  
|<span data-ttu-id="6165d-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="6165d-334">TABLE_NAME</span></span>|<span data-ttu-id="6165d-335">String</span><span class="sxs-lookup"><span data-stu-id="6165d-335">String</span></span>|  
|<span data-ttu-id="6165d-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="6165d-336">TABLE_TYPE</span></span>|<span data-ttu-id="6165d-337">String</span><span class="sxs-lookup"><span data-stu-id="6165d-337">String</span></span>|  
|<span data-ttu-id="6165d-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="6165d-338">TABLE_GUID</span></span>|<span data-ttu-id="6165d-339">Guid</span><span class="sxs-lookup"><span data-stu-id="6165d-339">Guid</span></span>|  
|<span data-ttu-id="6165d-340">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6165d-340">DESCRIPTION</span></span>|<span data-ttu-id="6165d-341">String</span><span class="sxs-lookup"><span data-stu-id="6165d-341">String</span></span>|  
|<span data-ttu-id="6165d-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="6165d-342">TABLE_PROPID</span></span>|<span data-ttu-id="6165d-343">Int64</span><span class="sxs-lookup"><span data-stu-id="6165d-343">Int64</span></span>|  
|<span data-ttu-id="6165d-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="6165d-344">DATE_CREATED</span></span>|<span data-ttu-id="6165d-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="6165d-345">DateTime</span></span>|  
|<span data-ttu-id="6165d-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="6165d-346">DATE_MODIFIED</span></span>|<span data-ttu-id="6165d-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="6165d-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="6165d-348">Столбцы</span><span class="sxs-lookup"><span data-stu-id="6165d-348">Columns</span></span>  
  
|<span data-ttu-id="6165d-349">ColumnName</span><span class="sxs-lookup"><span data-stu-id="6165d-349">ColumnName</span></span>|<span data-ttu-id="6165d-350">DataType</span><span class="sxs-lookup"><span data-stu-id="6165d-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="6165d-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="6165d-351">TABLE_CATALOG</span></span>|<span data-ttu-id="6165d-352">String</span><span class="sxs-lookup"><span data-stu-id="6165d-352">String</span></span>|  
|<span data-ttu-id="6165d-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="6165d-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="6165d-354">String</span><span class="sxs-lookup"><span data-stu-id="6165d-354">String</span></span>|  
|<span data-ttu-id="6165d-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="6165d-355">TABLE_NAME</span></span>|<span data-ttu-id="6165d-356">String</span><span class="sxs-lookup"><span data-stu-id="6165d-356">String</span></span>|  
|<span data-ttu-id="6165d-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="6165d-357">COLUMN_NAME</span></span>|<span data-ttu-id="6165d-358">String</span><span class="sxs-lookup"><span data-stu-id="6165d-358">String</span></span>|  
|<span data-ttu-id="6165d-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="6165d-359">COLUMN_GUID</span></span>|<span data-ttu-id="6165d-360">Guid</span><span class="sxs-lookup"><span data-stu-id="6165d-360">Guid</span></span>|  
|<span data-ttu-id="6165d-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="6165d-361">COLUMN_PROPID</span></span>|<span data-ttu-id="6165d-362">Int64</span><span class="sxs-lookup"><span data-stu-id="6165d-362">Int64</span></span>|  
|<span data-ttu-id="6165d-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="6165d-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="6165d-364">Int64</span><span class="sxs-lookup"><span data-stu-id="6165d-364">Int64</span></span>|  
|<span data-ttu-id="6165d-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="6165d-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="6165d-366">Boolean</span><span class="sxs-lookup"><span data-stu-id="6165d-366">Boolean</span></span>|  
|<span data-ttu-id="6165d-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="6165d-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="6165d-368">String</span><span class="sxs-lookup"><span data-stu-id="6165d-368">String</span></span>|  
|<span data-ttu-id="6165d-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="6165d-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="6165d-370">Int64</span><span class="sxs-lookup"><span data-stu-id="6165d-370">Int64</span></span>|  
|<span data-ttu-id="6165d-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="6165d-371">IS_NULLABLE</span></span>|<span data-ttu-id="6165d-372">Boolean</span><span class="sxs-lookup"><span data-stu-id="6165d-372">Boolean</span></span>|  
|<span data-ttu-id="6165d-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="6165d-373">DATA_TYPE</span></span>|<span data-ttu-id="6165d-374">Int32</span><span class="sxs-lookup"><span data-stu-id="6165d-374">Int32</span></span>|  
|<span data-ttu-id="6165d-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="6165d-375">TYPE_GUID</span></span>|<span data-ttu-id="6165d-376">Guid</span><span class="sxs-lookup"><span data-stu-id="6165d-376">Guid</span></span>|  
|<span data-ttu-id="6165d-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="6165d-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="6165d-378">Int64</span><span class="sxs-lookup"><span data-stu-id="6165d-378">Int64</span></span>|  
|<span data-ttu-id="6165d-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="6165d-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="6165d-380">Int64</span><span class="sxs-lookup"><span data-stu-id="6165d-380">Int64</span></span>|  
|<span data-ttu-id="6165d-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="6165d-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="6165d-382">Int32</span><span class="sxs-lookup"><span data-stu-id="6165d-382">Int32</span></span>|  
|<span data-ttu-id="6165d-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="6165d-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="6165d-384">Int16</span><span class="sxs-lookup"><span data-stu-id="6165d-384">Int16</span></span>|  
|<span data-ttu-id="6165d-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="6165d-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="6165d-386">Int64</span><span class="sxs-lookup"><span data-stu-id="6165d-386">Int64</span></span>|  
|<span data-ttu-id="6165d-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="6165d-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="6165d-388">String</span><span class="sxs-lookup"><span data-stu-id="6165d-388">String</span></span>|  
|<span data-ttu-id="6165d-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="6165d-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="6165d-390">String</span><span class="sxs-lookup"><span data-stu-id="6165d-390">String</span></span>|  
|<span data-ttu-id="6165d-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="6165d-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="6165d-392">String</span><span class="sxs-lookup"><span data-stu-id="6165d-392">String</span></span>|  
|<span data-ttu-id="6165d-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="6165d-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="6165d-394">String</span><span class="sxs-lookup"><span data-stu-id="6165d-394">String</span></span>|  
|<span data-ttu-id="6165d-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="6165d-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="6165d-396">String</span><span class="sxs-lookup"><span data-stu-id="6165d-396">String</span></span>|  
|<span data-ttu-id="6165d-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="6165d-397">COLLATION_NAME</span></span>|<span data-ttu-id="6165d-398">String</span><span class="sxs-lookup"><span data-stu-id="6165d-398">String</span></span>|  
|<span data-ttu-id="6165d-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="6165d-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="6165d-400">String</span><span class="sxs-lookup"><span data-stu-id="6165d-400">String</span></span>|  
|<span data-ttu-id="6165d-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="6165d-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="6165d-402">String</span><span class="sxs-lookup"><span data-stu-id="6165d-402">String</span></span>|  
|<span data-ttu-id="6165d-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="6165d-403">DOMAIN_NAME</span></span>|<span data-ttu-id="6165d-404">String</span><span class="sxs-lookup"><span data-stu-id="6165d-404">String</span></span>|  
|<span data-ttu-id="6165d-405">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6165d-405">DESCRIPTION</span></span>|<span data-ttu-id="6165d-406">String</span><span class="sxs-lookup"><span data-stu-id="6165d-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="6165d-407">Процедуры</span><span class="sxs-lookup"><span data-stu-id="6165d-407">Procedures</span></span>  
  
|<span data-ttu-id="6165d-408">ColumnName</span><span class="sxs-lookup"><span data-stu-id="6165d-408">ColumnName</span></span>|<span data-ttu-id="6165d-409">DataType</span><span class="sxs-lookup"><span data-stu-id="6165d-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="6165d-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="6165d-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="6165d-411">String</span><span class="sxs-lookup"><span data-stu-id="6165d-411">String</span></span>|  
|<span data-ttu-id="6165d-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="6165d-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="6165d-413">String</span><span class="sxs-lookup"><span data-stu-id="6165d-413">String</span></span>|  
|<span data-ttu-id="6165d-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="6165d-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="6165d-415">String</span><span class="sxs-lookup"><span data-stu-id="6165d-415">String</span></span>|  
|<span data-ttu-id="6165d-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="6165d-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="6165d-417">Int16</span><span class="sxs-lookup"><span data-stu-id="6165d-417">Int16</span></span>|  
|<span data-ttu-id="6165d-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="6165d-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="6165d-419">String</span><span class="sxs-lookup"><span data-stu-id="6165d-419">String</span></span>|  
|<span data-ttu-id="6165d-420">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6165d-420">DESCRIPTION</span></span>|<span data-ttu-id="6165d-421">String</span><span class="sxs-lookup"><span data-stu-id="6165d-421">String</span></span>|  
|<span data-ttu-id="6165d-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="6165d-422">DATE_CREATED</span></span>|<span data-ttu-id="6165d-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="6165d-423">DateTime</span></span>|  
|<span data-ttu-id="6165d-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="6165d-424">DATE_MODIFIED</span></span>|<span data-ttu-id="6165d-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="6165d-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="6165d-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="6165d-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="6165d-427">ColumnName</span><span class="sxs-lookup"><span data-stu-id="6165d-427">ColumnName</span></span>|<span data-ttu-id="6165d-428">DataType</span><span class="sxs-lookup"><span data-stu-id="6165d-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="6165d-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="6165d-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="6165d-430">String</span><span class="sxs-lookup"><span data-stu-id="6165d-430">String</span></span>|  
|<span data-ttu-id="6165d-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="6165d-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="6165d-432">String</span><span class="sxs-lookup"><span data-stu-id="6165d-432">String</span></span>|  
|<span data-ttu-id="6165d-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="6165d-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="6165d-434">String</span><span class="sxs-lookup"><span data-stu-id="6165d-434">String</span></span>|  
|<span data-ttu-id="6165d-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="6165d-435">COLUMN_NAME</span></span>|<span data-ttu-id="6165d-436">String</span><span class="sxs-lookup"><span data-stu-id="6165d-436">String</span></span>|  
|<span data-ttu-id="6165d-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="6165d-437">COLUMN_GUID</span></span>|<span data-ttu-id="6165d-438">Guid</span><span class="sxs-lookup"><span data-stu-id="6165d-438">Guid</span></span>|  
|<span data-ttu-id="6165d-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="6165d-439">COLUMN_PROPID</span></span>|<span data-ttu-id="6165d-440">Int64</span><span class="sxs-lookup"><span data-stu-id="6165d-440">Int64</span></span>|  
|<span data-ttu-id="6165d-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="6165d-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="6165d-442">Int64</span><span class="sxs-lookup"><span data-stu-id="6165d-442">Int64</span></span>|  
|<span data-ttu-id="6165d-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="6165d-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="6165d-444">Int64</span><span class="sxs-lookup"><span data-stu-id="6165d-444">Int64</span></span>|  
|<span data-ttu-id="6165d-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="6165d-445">IS_NULLABLE</span></span>|<span data-ttu-id="6165d-446">Boolean</span><span class="sxs-lookup"><span data-stu-id="6165d-446">Boolean</span></span>|  
|<span data-ttu-id="6165d-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="6165d-447">DATA_TYPE</span></span>|<span data-ttu-id="6165d-448">Int32</span><span class="sxs-lookup"><span data-stu-id="6165d-448">Int32</span></span>|  
|<span data-ttu-id="6165d-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="6165d-449">TYPE_GUID</span></span>|<span data-ttu-id="6165d-450">Guid</span><span class="sxs-lookup"><span data-stu-id="6165d-450">Guid</span></span>|  
|<span data-ttu-id="6165d-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="6165d-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="6165d-452">Int64</span><span class="sxs-lookup"><span data-stu-id="6165d-452">Int64</span></span>|  
|<span data-ttu-id="6165d-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="6165d-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="6165d-454">Int64</span><span class="sxs-lookup"><span data-stu-id="6165d-454">Int64</span></span>|  
|<span data-ttu-id="6165d-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="6165d-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="6165d-456">Int32</span><span class="sxs-lookup"><span data-stu-id="6165d-456">Int32</span></span>|  
|<span data-ttu-id="6165d-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="6165d-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="6165d-458">Int16</span><span class="sxs-lookup"><span data-stu-id="6165d-458">Int16</span></span>|  
|<span data-ttu-id="6165d-459">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6165d-459">DESCRIPTION</span></span>|<span data-ttu-id="6165d-460">String</span><span class="sxs-lookup"><span data-stu-id="6165d-460">String</span></span>|  
|<span data-ttu-id="6165d-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="6165d-461">OVERLOAD</span></span>|<span data-ttu-id="6165d-462">Int16</span><span class="sxs-lookup"><span data-stu-id="6165d-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="6165d-463">Представления</span><span class="sxs-lookup"><span data-stu-id="6165d-463">Views</span></span>  
  
|<span data-ttu-id="6165d-464">ColumnName</span><span class="sxs-lookup"><span data-stu-id="6165d-464">ColumnName</span></span>|<span data-ttu-id="6165d-465">DataType</span><span class="sxs-lookup"><span data-stu-id="6165d-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="6165d-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="6165d-466">TABLE_CATALOG</span></span>|<span data-ttu-id="6165d-467">String</span><span class="sxs-lookup"><span data-stu-id="6165d-467">String</span></span>|  
|<span data-ttu-id="6165d-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="6165d-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="6165d-469">String</span><span class="sxs-lookup"><span data-stu-id="6165d-469">String</span></span>|  
|<span data-ttu-id="6165d-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="6165d-470">TABLE_NAME</span></span>|<span data-ttu-id="6165d-471">String</span><span class="sxs-lookup"><span data-stu-id="6165d-471">String</span></span>|  
|<span data-ttu-id="6165d-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="6165d-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="6165d-473">String</span><span class="sxs-lookup"><span data-stu-id="6165d-473">String</span></span>|  
|<span data-ttu-id="6165d-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="6165d-474">CHECK_OPTION</span></span>|<span data-ttu-id="6165d-475">Boolean</span><span class="sxs-lookup"><span data-stu-id="6165d-475">Boolean</span></span>|  
|<span data-ttu-id="6165d-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="6165d-476">IS_UPDATABLE</span></span>|<span data-ttu-id="6165d-477">Boolean</span><span class="sxs-lookup"><span data-stu-id="6165d-477">Boolean</span></span>|  
|<span data-ttu-id="6165d-478">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6165d-478">DESCRIPTION</span></span>|<span data-ttu-id="6165d-479">String</span><span class="sxs-lookup"><span data-stu-id="6165d-479">String</span></span>|  
|<span data-ttu-id="6165d-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="6165d-480">DATE_CREATED</span></span>|<span data-ttu-id="6165d-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="6165d-481">DateTime</span></span>|  
|<span data-ttu-id="6165d-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="6165d-482">DATE_MODIFIED</span></span>|<span data-ttu-id="6165d-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="6165d-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="6165d-484">Индексы</span><span class="sxs-lookup"><span data-stu-id="6165d-484">Indexes</span></span>  
  
|<span data-ttu-id="6165d-485">ColumnName</span><span class="sxs-lookup"><span data-stu-id="6165d-485">ColumnName</span></span>|<span data-ttu-id="6165d-486">DataType</span><span class="sxs-lookup"><span data-stu-id="6165d-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="6165d-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="6165d-487">TABLE_CATALOG</span></span>|<span data-ttu-id="6165d-488">String</span><span class="sxs-lookup"><span data-stu-id="6165d-488">String</span></span>|  
|<span data-ttu-id="6165d-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="6165d-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="6165d-490">String</span><span class="sxs-lookup"><span data-stu-id="6165d-490">String</span></span>|  
|<span data-ttu-id="6165d-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="6165d-491">TABLE_NAME</span></span>|<span data-ttu-id="6165d-492">String</span><span class="sxs-lookup"><span data-stu-id="6165d-492">String</span></span>|  
|<span data-ttu-id="6165d-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="6165d-493">INDEX_CATALOG</span></span>|<span data-ttu-id="6165d-494">String</span><span class="sxs-lookup"><span data-stu-id="6165d-494">String</span></span>|  
|<span data-ttu-id="6165d-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="6165d-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="6165d-496">String</span><span class="sxs-lookup"><span data-stu-id="6165d-496">String</span></span>|  
|<span data-ttu-id="6165d-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="6165d-497">INDEX_NAME</span></span>|<span data-ttu-id="6165d-498">String</span><span class="sxs-lookup"><span data-stu-id="6165d-498">String</span></span>|  
|<span data-ttu-id="6165d-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="6165d-499">PRIMARY_KEY</span></span>|<span data-ttu-id="6165d-500">Boolean</span><span class="sxs-lookup"><span data-stu-id="6165d-500">Boolean</span></span>|  
|<span data-ttu-id="6165d-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="6165d-501">UNIQUE</span></span>|<span data-ttu-id="6165d-502">Boolean</span><span class="sxs-lookup"><span data-stu-id="6165d-502">Boolean</span></span>|  
|<span data-ttu-id="6165d-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="6165d-503">CLUSTERED</span></span>|<span data-ttu-id="6165d-504">Boolean</span><span class="sxs-lookup"><span data-stu-id="6165d-504">Boolean</span></span>|  
|<span data-ttu-id="6165d-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="6165d-505">TYPE</span></span>|<span data-ttu-id="6165d-506">Int32</span><span class="sxs-lookup"><span data-stu-id="6165d-506">Int32</span></span>|  
|<span data-ttu-id="6165d-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="6165d-507">FILL_FACTOR</span></span>|<span data-ttu-id="6165d-508">Int32</span><span class="sxs-lookup"><span data-stu-id="6165d-508">Int32</span></span>|  
|<span data-ttu-id="6165d-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="6165d-509">INITIAL_SIZE</span></span>|<span data-ttu-id="6165d-510">Int32</span><span class="sxs-lookup"><span data-stu-id="6165d-510">Int32</span></span>|  
|<span data-ttu-id="6165d-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="6165d-511">NULLS</span></span>|<span data-ttu-id="6165d-512">Int32</span><span class="sxs-lookup"><span data-stu-id="6165d-512">Int32</span></span>|  
|<span data-ttu-id="6165d-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="6165d-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="6165d-514">Boolean</span><span class="sxs-lookup"><span data-stu-id="6165d-514">Boolean</span></span>|  
|<span data-ttu-id="6165d-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="6165d-515">AUTO_UPDATE</span></span>|<span data-ttu-id="6165d-516">Boolean</span><span class="sxs-lookup"><span data-stu-id="6165d-516">Boolean</span></span>|  
|<span data-ttu-id="6165d-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="6165d-517">NULL_COLLATION</span></span>|<span data-ttu-id="6165d-518">Int32</span><span class="sxs-lookup"><span data-stu-id="6165d-518">Int32</span></span>|  
|<span data-ttu-id="6165d-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="6165d-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="6165d-520">Int64</span><span class="sxs-lookup"><span data-stu-id="6165d-520">Int64</span></span>|  
|<span data-ttu-id="6165d-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="6165d-521">COLUMN_NAME</span></span>|<span data-ttu-id="6165d-522">String</span><span class="sxs-lookup"><span data-stu-id="6165d-522">String</span></span>|  
|<span data-ttu-id="6165d-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="6165d-523">COLUMN_GUID</span></span>|<span data-ttu-id="6165d-524">Guid</span><span class="sxs-lookup"><span data-stu-id="6165d-524">Guid</span></span>|  
|<span data-ttu-id="6165d-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="6165d-525">COLUMN_PROPID</span></span>|<span data-ttu-id="6165d-526">Int64</span><span class="sxs-lookup"><span data-stu-id="6165d-526">Int64</span></span>|  
|<span data-ttu-id="6165d-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="6165d-527">COLLATION</span></span>|<span data-ttu-id="6165d-528">Int16</span><span class="sxs-lookup"><span data-stu-id="6165d-528">Int16</span></span>|  
|<span data-ttu-id="6165d-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="6165d-529">CARDINALITY</span></span>|<span data-ttu-id="6165d-530">Десятичное число</span><span class="sxs-lookup"><span data-stu-id="6165d-530">Decimal</span></span>|  
|<span data-ttu-id="6165d-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="6165d-531">PAGES</span></span>|<span data-ttu-id="6165d-532">Int32</span><span class="sxs-lookup"><span data-stu-id="6165d-532">Int32</span></span>|  
|<span data-ttu-id="6165d-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="6165d-533">FILTER_CONDITION</span></span>|<span data-ttu-id="6165d-534">String</span><span class="sxs-lookup"><span data-stu-id="6165d-534">String</span></span>|  
|<span data-ttu-id="6165d-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="6165d-535">INTEGRATED</span></span>|<span data-ttu-id="6165d-536">Boolean</span><span class="sxs-lookup"><span data-stu-id="6165d-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="6165d-537">Поставщик OLE DB для Microsoft Jet</span><span class="sxs-lookup"><span data-stu-id="6165d-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="6165d-538">Драйвер OLE DB для Jet (Майкрософт) поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.</span><span class="sxs-lookup"><span data-stu-id="6165d-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="6165d-539">Таблицы</span><span class="sxs-lookup"><span data-stu-id="6165d-539">Tables</span></span>  
  
- <span data-ttu-id="6165d-540">Столбцы</span><span class="sxs-lookup"><span data-stu-id="6165d-540">Columns</span></span>  
  
- <span data-ttu-id="6165d-541">Процедуры</span><span class="sxs-lookup"><span data-stu-id="6165d-541">Procedures</span></span>  
  
- <span data-ttu-id="6165d-542">Представления</span><span class="sxs-lookup"><span data-stu-id="6165d-542">Views</span></span>  
  
- <span data-ttu-id="6165d-543">Индексы</span><span class="sxs-lookup"><span data-stu-id="6165d-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="6165d-544">Таблицы</span><span class="sxs-lookup"><span data-stu-id="6165d-544">Tables</span></span>  
  
|<span data-ttu-id="6165d-545">ColumnName</span><span class="sxs-lookup"><span data-stu-id="6165d-545">ColumnName</span></span>|<span data-ttu-id="6165d-546">DataType</span><span class="sxs-lookup"><span data-stu-id="6165d-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="6165d-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="6165d-547">TABLE_CATALOG</span></span>|<span data-ttu-id="6165d-548">String</span><span class="sxs-lookup"><span data-stu-id="6165d-548">String</span></span>|  
|<span data-ttu-id="6165d-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="6165d-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="6165d-550">String</span><span class="sxs-lookup"><span data-stu-id="6165d-550">String</span></span>|  
|<span data-ttu-id="6165d-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="6165d-551">TABLE_NAME</span></span>|<span data-ttu-id="6165d-552">String</span><span class="sxs-lookup"><span data-stu-id="6165d-552">String</span></span>|  
|<span data-ttu-id="6165d-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="6165d-553">TABLE_TYPE</span></span>|<span data-ttu-id="6165d-554">String</span><span class="sxs-lookup"><span data-stu-id="6165d-554">String</span></span>|  
|<span data-ttu-id="6165d-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="6165d-555">TABLE_GUID</span></span>|<span data-ttu-id="6165d-556">Guid</span><span class="sxs-lookup"><span data-stu-id="6165d-556">Guid</span></span>|  
|<span data-ttu-id="6165d-557">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6165d-557">DESCRIPTION</span></span>|<span data-ttu-id="6165d-558">String</span><span class="sxs-lookup"><span data-stu-id="6165d-558">String</span></span>|  
|<span data-ttu-id="6165d-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="6165d-559">TABLE_PROPID</span></span>|<span data-ttu-id="6165d-560">Int64</span><span class="sxs-lookup"><span data-stu-id="6165d-560">Int64</span></span>|  
|<span data-ttu-id="6165d-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="6165d-561">DATE_CREATED</span></span>|<span data-ttu-id="6165d-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="6165d-562">DateTime</span></span>|  
|<span data-ttu-id="6165d-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="6165d-563">DATE_MODIFIED</span></span>|<span data-ttu-id="6165d-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="6165d-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="6165d-565">Столбцы</span><span class="sxs-lookup"><span data-stu-id="6165d-565">Columns</span></span>  
  
|<span data-ttu-id="6165d-566">ColumnName</span><span class="sxs-lookup"><span data-stu-id="6165d-566">ColumnName</span></span>|<span data-ttu-id="6165d-567">DataType</span><span class="sxs-lookup"><span data-stu-id="6165d-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="6165d-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="6165d-568">TABLE_CATALOG</span></span>|<span data-ttu-id="6165d-569">String</span><span class="sxs-lookup"><span data-stu-id="6165d-569">String</span></span>|  
|<span data-ttu-id="6165d-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="6165d-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="6165d-571">String</span><span class="sxs-lookup"><span data-stu-id="6165d-571">String</span></span>|  
|<span data-ttu-id="6165d-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="6165d-572">TABLE_NAME</span></span>|<span data-ttu-id="6165d-573">String</span><span class="sxs-lookup"><span data-stu-id="6165d-573">String</span></span>|  
|<span data-ttu-id="6165d-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="6165d-574">COLUMN_NAME</span></span>|<span data-ttu-id="6165d-575">String</span><span class="sxs-lookup"><span data-stu-id="6165d-575">String</span></span>|  
|<span data-ttu-id="6165d-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="6165d-576">COLUMN_GUID</span></span>|<span data-ttu-id="6165d-577">Guid</span><span class="sxs-lookup"><span data-stu-id="6165d-577">Guid</span></span>|  
|<span data-ttu-id="6165d-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="6165d-578">COLUMN_PROPID</span></span>|<span data-ttu-id="6165d-579">Int64</span><span class="sxs-lookup"><span data-stu-id="6165d-579">Int64</span></span>|  
|<span data-ttu-id="6165d-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="6165d-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="6165d-581">Int64</span><span class="sxs-lookup"><span data-stu-id="6165d-581">Int64</span></span>|  
|<span data-ttu-id="6165d-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="6165d-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="6165d-583">Boolean</span><span class="sxs-lookup"><span data-stu-id="6165d-583">Boolean</span></span>|  
|<span data-ttu-id="6165d-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="6165d-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="6165d-585">String</span><span class="sxs-lookup"><span data-stu-id="6165d-585">String</span></span>|  
|<span data-ttu-id="6165d-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="6165d-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="6165d-587">Int64</span><span class="sxs-lookup"><span data-stu-id="6165d-587">Int64</span></span>|  
|<span data-ttu-id="6165d-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="6165d-588">IS_NULLABLE</span></span>|<span data-ttu-id="6165d-589">Boolean</span><span class="sxs-lookup"><span data-stu-id="6165d-589">Boolean</span></span>|  
|<span data-ttu-id="6165d-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="6165d-590">DATA_TYPE</span></span>|<span data-ttu-id="6165d-591">Int32</span><span class="sxs-lookup"><span data-stu-id="6165d-591">Int32</span></span>|  
|<span data-ttu-id="6165d-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="6165d-592">TYPE_GUID</span></span>|<span data-ttu-id="6165d-593">Guid</span><span class="sxs-lookup"><span data-stu-id="6165d-593">Guid</span></span>|  
|<span data-ttu-id="6165d-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="6165d-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="6165d-595">Int64</span><span class="sxs-lookup"><span data-stu-id="6165d-595">Int64</span></span>|  
|<span data-ttu-id="6165d-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="6165d-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="6165d-597">Int64</span><span class="sxs-lookup"><span data-stu-id="6165d-597">Int64</span></span>|  
|<span data-ttu-id="6165d-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="6165d-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="6165d-599">Int32</span><span class="sxs-lookup"><span data-stu-id="6165d-599">Int32</span></span>|  
|<span data-ttu-id="6165d-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="6165d-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="6165d-601">Int16</span><span class="sxs-lookup"><span data-stu-id="6165d-601">Int16</span></span>|  
|<span data-ttu-id="6165d-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="6165d-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="6165d-603">Int64</span><span class="sxs-lookup"><span data-stu-id="6165d-603">Int64</span></span>|  
|<span data-ttu-id="6165d-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="6165d-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="6165d-605">String</span><span class="sxs-lookup"><span data-stu-id="6165d-605">String</span></span>|  
|<span data-ttu-id="6165d-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="6165d-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="6165d-607">String</span><span class="sxs-lookup"><span data-stu-id="6165d-607">String</span></span>|  
|<span data-ttu-id="6165d-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="6165d-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="6165d-609">String</span><span class="sxs-lookup"><span data-stu-id="6165d-609">String</span></span>|  
|<span data-ttu-id="6165d-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="6165d-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="6165d-611">String</span><span class="sxs-lookup"><span data-stu-id="6165d-611">String</span></span>|  
|<span data-ttu-id="6165d-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="6165d-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="6165d-613">String</span><span class="sxs-lookup"><span data-stu-id="6165d-613">String</span></span>|  
|<span data-ttu-id="6165d-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="6165d-614">COLLATION_NAME</span></span>|<span data-ttu-id="6165d-615">String</span><span class="sxs-lookup"><span data-stu-id="6165d-615">String</span></span>|  
|<span data-ttu-id="6165d-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="6165d-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="6165d-617">String</span><span class="sxs-lookup"><span data-stu-id="6165d-617">String</span></span>|  
|<span data-ttu-id="6165d-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="6165d-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="6165d-619">String</span><span class="sxs-lookup"><span data-stu-id="6165d-619">String</span></span>|  
|<span data-ttu-id="6165d-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="6165d-620">DOMAIN_NAME</span></span>|<span data-ttu-id="6165d-621">String</span><span class="sxs-lookup"><span data-stu-id="6165d-621">String</span></span>|  
|<span data-ttu-id="6165d-622">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6165d-622">DESCRIPTION</span></span>|<span data-ttu-id="6165d-623">String</span><span class="sxs-lookup"><span data-stu-id="6165d-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="6165d-624">Процедуры</span><span class="sxs-lookup"><span data-stu-id="6165d-624">Procedures</span></span>  
  
|<span data-ttu-id="6165d-625">ColumnName</span><span class="sxs-lookup"><span data-stu-id="6165d-625">ColumnName</span></span>|<span data-ttu-id="6165d-626">DataType</span><span class="sxs-lookup"><span data-stu-id="6165d-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="6165d-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="6165d-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="6165d-628">String</span><span class="sxs-lookup"><span data-stu-id="6165d-628">String</span></span>|  
|<span data-ttu-id="6165d-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="6165d-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="6165d-630">String</span><span class="sxs-lookup"><span data-stu-id="6165d-630">String</span></span>|  
|<span data-ttu-id="6165d-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="6165d-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="6165d-632">String</span><span class="sxs-lookup"><span data-stu-id="6165d-632">String</span></span>|  
|<span data-ttu-id="6165d-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="6165d-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="6165d-634">Int16</span><span class="sxs-lookup"><span data-stu-id="6165d-634">Int16</span></span>|  
|<span data-ttu-id="6165d-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="6165d-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="6165d-636">String</span><span class="sxs-lookup"><span data-stu-id="6165d-636">String</span></span>|  
|<span data-ttu-id="6165d-637">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6165d-637">DESCRIPTION</span></span>|<span data-ttu-id="6165d-638">String</span><span class="sxs-lookup"><span data-stu-id="6165d-638">String</span></span>|  
|<span data-ttu-id="6165d-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="6165d-639">DATE_CREATED</span></span>|<span data-ttu-id="6165d-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="6165d-640">DateTime</span></span>|  
|<span data-ttu-id="6165d-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="6165d-641">DATE_MODIFIED</span></span>|<span data-ttu-id="6165d-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="6165d-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="6165d-643">Представления</span><span class="sxs-lookup"><span data-stu-id="6165d-643">Views</span></span>  
  
|<span data-ttu-id="6165d-644">ColumnName</span><span class="sxs-lookup"><span data-stu-id="6165d-644">ColumnName</span></span>|<span data-ttu-id="6165d-645">DataType</span><span class="sxs-lookup"><span data-stu-id="6165d-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="6165d-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="6165d-646">TABLE_CATALOG</span></span>|<span data-ttu-id="6165d-647">String</span><span class="sxs-lookup"><span data-stu-id="6165d-647">String</span></span>|  
|<span data-ttu-id="6165d-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="6165d-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="6165d-649">String</span><span class="sxs-lookup"><span data-stu-id="6165d-649">String</span></span>|  
|<span data-ttu-id="6165d-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="6165d-650">TABLE_NAME</span></span>|<span data-ttu-id="6165d-651">String</span><span class="sxs-lookup"><span data-stu-id="6165d-651">String</span></span>|  
|<span data-ttu-id="6165d-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="6165d-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="6165d-653">String</span><span class="sxs-lookup"><span data-stu-id="6165d-653">String</span></span>|  
|<span data-ttu-id="6165d-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="6165d-654">CHECK_OPTION</span></span>|<span data-ttu-id="6165d-655">Boolean</span><span class="sxs-lookup"><span data-stu-id="6165d-655">Boolean</span></span>|  
|<span data-ttu-id="6165d-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="6165d-656">IS_UPDATABLE</span></span>|<span data-ttu-id="6165d-657">Boolean</span><span class="sxs-lookup"><span data-stu-id="6165d-657">Boolean</span></span>|  
|<span data-ttu-id="6165d-658">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6165d-658">DESCRIPTION</span></span>|<span data-ttu-id="6165d-659">String</span><span class="sxs-lookup"><span data-stu-id="6165d-659">String</span></span>|  
|<span data-ttu-id="6165d-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="6165d-660">DATE_CREATED</span></span>|<span data-ttu-id="6165d-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="6165d-661">DateTime</span></span>|  
|<span data-ttu-id="6165d-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="6165d-662">DATE_MODIFIED</span></span>|<span data-ttu-id="6165d-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="6165d-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="6165d-664">Индексы</span><span class="sxs-lookup"><span data-stu-id="6165d-664">Indexes</span></span>  
  
|<span data-ttu-id="6165d-665">ColumnName</span><span class="sxs-lookup"><span data-stu-id="6165d-665">ColumnName</span></span>|<span data-ttu-id="6165d-666">DataType</span><span class="sxs-lookup"><span data-stu-id="6165d-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="6165d-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="6165d-667">TABLE_CATALOG</span></span>|<span data-ttu-id="6165d-668">String</span><span class="sxs-lookup"><span data-stu-id="6165d-668">String</span></span>|  
|<span data-ttu-id="6165d-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="6165d-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="6165d-670">String</span><span class="sxs-lookup"><span data-stu-id="6165d-670">String</span></span>|  
|<span data-ttu-id="6165d-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="6165d-671">TABLE_NAME</span></span>|<span data-ttu-id="6165d-672">String</span><span class="sxs-lookup"><span data-stu-id="6165d-672">String</span></span>|  
|<span data-ttu-id="6165d-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="6165d-673">INDEX_CATALOG</span></span>|<span data-ttu-id="6165d-674">String</span><span class="sxs-lookup"><span data-stu-id="6165d-674">String</span></span>|  
|<span data-ttu-id="6165d-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="6165d-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="6165d-676">String</span><span class="sxs-lookup"><span data-stu-id="6165d-676">String</span></span>|  
|<span data-ttu-id="6165d-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="6165d-677">INDEX_NAME</span></span>|<span data-ttu-id="6165d-678">String</span><span class="sxs-lookup"><span data-stu-id="6165d-678">String</span></span>|  
|<span data-ttu-id="6165d-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="6165d-679">PRIMARY_KEY</span></span>|<span data-ttu-id="6165d-680">Boolean</span><span class="sxs-lookup"><span data-stu-id="6165d-680">Boolean</span></span>|  
|<span data-ttu-id="6165d-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="6165d-681">UNIQUE</span></span>|<span data-ttu-id="6165d-682">Boolean</span><span class="sxs-lookup"><span data-stu-id="6165d-682">Boolean</span></span>|  
|<span data-ttu-id="6165d-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="6165d-683">CLUSTERED</span></span>|<span data-ttu-id="6165d-684">Boolean</span><span class="sxs-lookup"><span data-stu-id="6165d-684">Boolean</span></span>|  
|<span data-ttu-id="6165d-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="6165d-685">TYPE</span></span>|<span data-ttu-id="6165d-686">Int32</span><span class="sxs-lookup"><span data-stu-id="6165d-686">Int32</span></span>|  
|<span data-ttu-id="6165d-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="6165d-687">FILL_FACTOR</span></span>|<span data-ttu-id="6165d-688">Int32</span><span class="sxs-lookup"><span data-stu-id="6165d-688">Int32</span></span>|  
|<span data-ttu-id="6165d-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="6165d-689">INITIAL_SIZE</span></span>|<span data-ttu-id="6165d-690">Int32</span><span class="sxs-lookup"><span data-stu-id="6165d-690">Int32</span></span>|  
|<span data-ttu-id="6165d-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="6165d-691">NULLS</span></span>|<span data-ttu-id="6165d-692">Int32</span><span class="sxs-lookup"><span data-stu-id="6165d-692">Int32</span></span>|  
|<span data-ttu-id="6165d-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="6165d-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="6165d-694">Boolean</span><span class="sxs-lookup"><span data-stu-id="6165d-694">Boolean</span></span>|  
|<span data-ttu-id="6165d-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="6165d-695">AUTO_UPDATE</span></span>|<span data-ttu-id="6165d-696">Boolean</span><span class="sxs-lookup"><span data-stu-id="6165d-696">Boolean</span></span>|  
|<span data-ttu-id="6165d-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="6165d-697">NULL_COLLATION</span></span>|<span data-ttu-id="6165d-698">Int32</span><span class="sxs-lookup"><span data-stu-id="6165d-698">Int32</span></span>|  
|<span data-ttu-id="6165d-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="6165d-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="6165d-700">Int64</span><span class="sxs-lookup"><span data-stu-id="6165d-700">Int64</span></span>|  
|<span data-ttu-id="6165d-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="6165d-701">COLUMN_NAME</span></span>|<span data-ttu-id="6165d-702">String</span><span class="sxs-lookup"><span data-stu-id="6165d-702">String</span></span>|  
|<span data-ttu-id="6165d-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="6165d-703">COLUMN_GUID</span></span>|<span data-ttu-id="6165d-704">Guid</span><span class="sxs-lookup"><span data-stu-id="6165d-704">Guid</span></span>|  
|<span data-ttu-id="6165d-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="6165d-705">COLUMN_PROPID</span></span>|<span data-ttu-id="6165d-706">Int64</span><span class="sxs-lookup"><span data-stu-id="6165d-706">Int64</span></span>|  
|<span data-ttu-id="6165d-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="6165d-707">COLLATION</span></span>|<span data-ttu-id="6165d-708">Int16</span><span class="sxs-lookup"><span data-stu-id="6165d-708">Int16</span></span>|  
|<span data-ttu-id="6165d-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="6165d-709">CARDINALITY</span></span>|<span data-ttu-id="6165d-710">Десятичное число</span><span class="sxs-lookup"><span data-stu-id="6165d-710">Decimal</span></span>|  
|<span data-ttu-id="6165d-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="6165d-711">PAGES</span></span>|<span data-ttu-id="6165d-712">Int32</span><span class="sxs-lookup"><span data-stu-id="6165d-712">Int32</span></span>|  
|<span data-ttu-id="6165d-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="6165d-713">FILTER_CONDITION</span></span>|<span data-ttu-id="6165d-714">String</span><span class="sxs-lookup"><span data-stu-id="6165d-714">String</span></span>|  
|<span data-ttu-id="6165d-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="6165d-715">INTEGRATED</span></span>|<span data-ttu-id="6165d-716">Boolean</span><span class="sxs-lookup"><span data-stu-id="6165d-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6165d-717">См. также</span><span class="sxs-lookup"><span data-stu-id="6165d-717">See also</span></span>

- [<span data-ttu-id="6165d-718">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="6165d-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
