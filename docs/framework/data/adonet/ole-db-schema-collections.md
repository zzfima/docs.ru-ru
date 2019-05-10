---
title: Коллекции схемы OLE DB
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: 6c3441e86d4c5267418cf8002ba17d539c464d5c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64645898"
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="711db-102">Коллекции схемы OLE DB</span><span class="sxs-lookup"><span data-stu-id="711db-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="711db-103">В данном разделе рассматривается поддержка коллекций схем для поставщиков OLE DB для Microsoft SQL Server, Oracle и Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="711db-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="711db-104">Поставщик OLE DB для Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="711db-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="711db-105">Драйвер Microsoft SQL Server OLE DB поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.</span><span class="sxs-lookup"><span data-stu-id="711db-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="711db-106">Таблицы</span><span class="sxs-lookup"><span data-stu-id="711db-106">Tables</span></span>  
  
- <span data-ttu-id="711db-107">Столбцы</span><span class="sxs-lookup"><span data-stu-id="711db-107">Columns</span></span>  
  
- <span data-ttu-id="711db-108">Процедуры</span><span class="sxs-lookup"><span data-stu-id="711db-108">Procedures</span></span>  
  
- <span data-ttu-id="711db-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="711db-109">ProcedureParameters</span></span>  
  
- <span data-ttu-id="711db-110">Catalog</span><span class="sxs-lookup"><span data-stu-id="711db-110">Catalog</span></span>  
  
- <span data-ttu-id="711db-111">Индексы</span><span class="sxs-lookup"><span data-stu-id="711db-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="711db-112">Таблицы</span><span class="sxs-lookup"><span data-stu-id="711db-112">Tables</span></span>  
  
|<span data-ttu-id="711db-113">ColumnName</span><span class="sxs-lookup"><span data-stu-id="711db-113">ColumnName</span></span>|<span data-ttu-id="711db-114">DataType</span><span class="sxs-lookup"><span data-stu-id="711db-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="711db-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="711db-115">TABLE_CATALOG</span></span>|<span data-ttu-id="711db-116">String</span><span class="sxs-lookup"><span data-stu-id="711db-116">String</span></span>|  
|<span data-ttu-id="711db-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="711db-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="711db-118">String</span><span class="sxs-lookup"><span data-stu-id="711db-118">String</span></span>|  
|<span data-ttu-id="711db-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="711db-119">TABLE_NAME</span></span>|<span data-ttu-id="711db-120">String</span><span class="sxs-lookup"><span data-stu-id="711db-120">String</span></span>|  
|<span data-ttu-id="711db-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="711db-121">TABLE_TYPE</span></span>|<span data-ttu-id="711db-122">String</span><span class="sxs-lookup"><span data-stu-id="711db-122">String</span></span>|  
|<span data-ttu-id="711db-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="711db-123">TABLE_GUID</span></span>|<span data-ttu-id="711db-124">Guid</span><span class="sxs-lookup"><span data-stu-id="711db-124">Guid</span></span>|  
|<span data-ttu-id="711db-125">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="711db-125">DESCRIPTION</span></span>|<span data-ttu-id="711db-126">String</span><span class="sxs-lookup"><span data-stu-id="711db-126">String</span></span>|  
|<span data-ttu-id="711db-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="711db-127">TABLE_PROPID</span></span>|<span data-ttu-id="711db-128">Int64</span><span class="sxs-lookup"><span data-stu-id="711db-128">Int64</span></span>|  
|<span data-ttu-id="711db-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="711db-129">DATE_CREATED</span></span>|<span data-ttu-id="711db-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="711db-130">DateTime</span></span>|  
|<span data-ttu-id="711db-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="711db-131">DATE_MODIFIED</span></span>|<span data-ttu-id="711db-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="711db-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="711db-133">Столбцы</span><span class="sxs-lookup"><span data-stu-id="711db-133">Columns</span></span>  
  
|<span data-ttu-id="711db-134">ColumnName</span><span class="sxs-lookup"><span data-stu-id="711db-134">ColumnName</span></span>|<span data-ttu-id="711db-135">DataType</span><span class="sxs-lookup"><span data-stu-id="711db-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="711db-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="711db-136">TABLE_CATALOG</span></span>|<span data-ttu-id="711db-137">String</span><span class="sxs-lookup"><span data-stu-id="711db-137">String</span></span>|  
|<span data-ttu-id="711db-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="711db-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="711db-139">String</span><span class="sxs-lookup"><span data-stu-id="711db-139">String</span></span>|  
|<span data-ttu-id="711db-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="711db-140">TABLE_NAME</span></span>|<span data-ttu-id="711db-141">String</span><span class="sxs-lookup"><span data-stu-id="711db-141">String</span></span>|  
|<span data-ttu-id="711db-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="711db-142">COLUMN_NAME</span></span>|<span data-ttu-id="711db-143">String</span><span class="sxs-lookup"><span data-stu-id="711db-143">String</span></span>|  
|<span data-ttu-id="711db-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="711db-144">COLUMN_GUID</span></span>|<span data-ttu-id="711db-145">Guid</span><span class="sxs-lookup"><span data-stu-id="711db-145">Guid</span></span>|  
|<span data-ttu-id="711db-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="711db-146">COLUMN_PROPID</span></span>|<span data-ttu-id="711db-147">Int64</span><span class="sxs-lookup"><span data-stu-id="711db-147">Int64</span></span>|  
|<span data-ttu-id="711db-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="711db-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="711db-149">Int64</span><span class="sxs-lookup"><span data-stu-id="711db-149">Int64</span></span>|  
|<span data-ttu-id="711db-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="711db-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="711db-151">Boolean</span><span class="sxs-lookup"><span data-stu-id="711db-151">Boolean</span></span>|  
|<span data-ttu-id="711db-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="711db-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="711db-153">String</span><span class="sxs-lookup"><span data-stu-id="711db-153">String</span></span>|  
|<span data-ttu-id="711db-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="711db-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="711db-155">Int64</span><span class="sxs-lookup"><span data-stu-id="711db-155">Int64</span></span>|  
|<span data-ttu-id="711db-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="711db-156">IS_NULLABLE</span></span>|<span data-ttu-id="711db-157">Boolean</span><span class="sxs-lookup"><span data-stu-id="711db-157">Boolean</span></span>|  
|<span data-ttu-id="711db-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="711db-158">DATA_TYPE</span></span>|<span data-ttu-id="711db-159">Int32</span><span class="sxs-lookup"><span data-stu-id="711db-159">Int32</span></span>|  
|<span data-ttu-id="711db-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="711db-160">TYPE_GUID</span></span>|<span data-ttu-id="711db-161">Guid</span><span class="sxs-lookup"><span data-stu-id="711db-161">Guid</span></span>|  
|<span data-ttu-id="711db-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="711db-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="711db-163">Int64</span><span class="sxs-lookup"><span data-stu-id="711db-163">Int64</span></span>|  
|<span data-ttu-id="711db-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="711db-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="711db-165">Int64</span><span class="sxs-lookup"><span data-stu-id="711db-165">Int64</span></span>|  
|<span data-ttu-id="711db-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="711db-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="711db-167">Int32</span><span class="sxs-lookup"><span data-stu-id="711db-167">Int32</span></span>|  
|<span data-ttu-id="711db-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="711db-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="711db-169">Int16</span><span class="sxs-lookup"><span data-stu-id="711db-169">Int16</span></span>|  
|<span data-ttu-id="711db-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="711db-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="711db-171">Int64</span><span class="sxs-lookup"><span data-stu-id="711db-171">Int64</span></span>|  
|<span data-ttu-id="711db-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="711db-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="711db-173">String</span><span class="sxs-lookup"><span data-stu-id="711db-173">String</span></span>|  
|<span data-ttu-id="711db-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="711db-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="711db-175">String</span><span class="sxs-lookup"><span data-stu-id="711db-175">String</span></span>|  
|<span data-ttu-id="711db-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="711db-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="711db-177">String</span><span class="sxs-lookup"><span data-stu-id="711db-177">String</span></span>|  
|<span data-ttu-id="711db-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="711db-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="711db-179">String</span><span class="sxs-lookup"><span data-stu-id="711db-179">String</span></span>|  
|<span data-ttu-id="711db-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="711db-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="711db-181">String</span><span class="sxs-lookup"><span data-stu-id="711db-181">String</span></span>|  
|<span data-ttu-id="711db-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="711db-182">COLLATION_NAME</span></span>|<span data-ttu-id="711db-183">String</span><span class="sxs-lookup"><span data-stu-id="711db-183">String</span></span>|  
|<span data-ttu-id="711db-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="711db-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="711db-185">String</span><span class="sxs-lookup"><span data-stu-id="711db-185">String</span></span>|  
|<span data-ttu-id="711db-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="711db-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="711db-187">String</span><span class="sxs-lookup"><span data-stu-id="711db-187">String</span></span>|  
|<span data-ttu-id="711db-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="711db-188">DOMAIN_NAME</span></span>|<span data-ttu-id="711db-189">String</span><span class="sxs-lookup"><span data-stu-id="711db-189">String</span></span>|  
|<span data-ttu-id="711db-190">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="711db-190">DESCRIPTION</span></span>|<span data-ttu-id="711db-191">String</span><span class="sxs-lookup"><span data-stu-id="711db-191">String</span></span>|  
|<span data-ttu-id="711db-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="711db-192">COLUMN_LCID</span></span>|<span data-ttu-id="711db-193">Int32</span><span class="sxs-lookup"><span data-stu-id="711db-193">Int32</span></span>|  
|<span data-ttu-id="711db-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="711db-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="711db-195">Int32</span><span class="sxs-lookup"><span data-stu-id="711db-195">Int32</span></span>|  
|<span data-ttu-id="711db-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="711db-196">COLUMN_SORTID</span></span>|<span data-ttu-id="711db-197">Int32</span><span class="sxs-lookup"><span data-stu-id="711db-197">Int32</span></span>|  
|<span data-ttu-id="711db-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="711db-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="711db-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="711db-199">Byte[]</span></span>|  
|<span data-ttu-id="711db-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="711db-200">IS_COMPUTED</span></span>|<span data-ttu-id="711db-201">Boolean</span><span class="sxs-lookup"><span data-stu-id="711db-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="711db-202">Процедуры</span><span class="sxs-lookup"><span data-stu-id="711db-202">Procedures</span></span>  
  
|<span data-ttu-id="711db-203">ColumnName</span><span class="sxs-lookup"><span data-stu-id="711db-203">ColumnName</span></span>|<span data-ttu-id="711db-204">DataType</span><span class="sxs-lookup"><span data-stu-id="711db-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="711db-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="711db-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="711db-206">String</span><span class="sxs-lookup"><span data-stu-id="711db-206">String</span></span>|  
|<span data-ttu-id="711db-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="711db-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="711db-208">String</span><span class="sxs-lookup"><span data-stu-id="711db-208">String</span></span>|  
|<span data-ttu-id="711db-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="711db-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="711db-210">String</span><span class="sxs-lookup"><span data-stu-id="711db-210">String</span></span>|  
|<span data-ttu-id="711db-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="711db-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="711db-212">Int16</span><span class="sxs-lookup"><span data-stu-id="711db-212">Int16</span></span>|  
|<span data-ttu-id="711db-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="711db-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="711db-214">String</span><span class="sxs-lookup"><span data-stu-id="711db-214">String</span></span>|  
|<span data-ttu-id="711db-215">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="711db-215">DESCRIPTION</span></span>|<span data-ttu-id="711db-216">String</span><span class="sxs-lookup"><span data-stu-id="711db-216">String</span></span>|  
|<span data-ttu-id="711db-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="711db-217">DATE_CREATED</span></span>|<span data-ttu-id="711db-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="711db-218">DateTime</span></span>|  
|<span data-ttu-id="711db-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="711db-219">DATE_MODIFIED</span></span>|<span data-ttu-id="711db-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="711db-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="711db-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="711db-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="711db-222">ColumnName</span><span class="sxs-lookup"><span data-stu-id="711db-222">ColumnName</span></span>|<span data-ttu-id="711db-223">DataType</span><span class="sxs-lookup"><span data-stu-id="711db-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="711db-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="711db-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="711db-225">String</span><span class="sxs-lookup"><span data-stu-id="711db-225">String</span></span>|  
|<span data-ttu-id="711db-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="711db-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="711db-227">String</span><span class="sxs-lookup"><span data-stu-id="711db-227">String</span></span>|  
|<span data-ttu-id="711db-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="711db-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="711db-229">String</span><span class="sxs-lookup"><span data-stu-id="711db-229">String</span></span>|  
|<span data-ttu-id="711db-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="711db-230">PARAMETER_NAME</span></span>|<span data-ttu-id="711db-231">String</span><span class="sxs-lookup"><span data-stu-id="711db-231">String</span></span>|  
|<span data-ttu-id="711db-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="711db-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="711db-233">Int32</span><span class="sxs-lookup"><span data-stu-id="711db-233">Int32</span></span>|  
|<span data-ttu-id="711db-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="711db-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="711db-235">Int32</span><span class="sxs-lookup"><span data-stu-id="711db-235">Int32</span></span>|  
|<span data-ttu-id="711db-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="711db-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="711db-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="711db-237">Boolean</span></span>|  
|<span data-ttu-id="711db-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="711db-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="711db-239">String</span><span class="sxs-lookup"><span data-stu-id="711db-239">String</span></span>|  
|<span data-ttu-id="711db-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="711db-240">IS_NULLABLE</span></span>|<span data-ttu-id="711db-241">Boolean</span><span class="sxs-lookup"><span data-stu-id="711db-241">Boolean</span></span>|  
|<span data-ttu-id="711db-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="711db-242">DATA_TYPE</span></span>|<span data-ttu-id="711db-243">Int32</span><span class="sxs-lookup"><span data-stu-id="711db-243">Int32</span></span>|  
|<span data-ttu-id="711db-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="711db-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="711db-245">Int64</span><span class="sxs-lookup"><span data-stu-id="711db-245">Int64</span></span>|  
|<span data-ttu-id="711db-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="711db-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="711db-247">Int64</span><span class="sxs-lookup"><span data-stu-id="711db-247">Int64</span></span>|  
|<span data-ttu-id="711db-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="711db-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="711db-249">Int32</span><span class="sxs-lookup"><span data-stu-id="711db-249">Int32</span></span>|  
|<span data-ttu-id="711db-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="711db-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="711db-251">Int16</span><span class="sxs-lookup"><span data-stu-id="711db-251">Int16</span></span>|  
|<span data-ttu-id="711db-252">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="711db-252">DESCRIPTION</span></span>|<span data-ttu-id="711db-253">String</span><span class="sxs-lookup"><span data-stu-id="711db-253">String</span></span>|  
|<span data-ttu-id="711db-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="711db-254">TYPE_NAME</span></span>|<span data-ttu-id="711db-255">String</span><span class="sxs-lookup"><span data-stu-id="711db-255">String</span></span>|  
|<span data-ttu-id="711db-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="711db-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="711db-257">String</span><span class="sxs-lookup"><span data-stu-id="711db-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="711db-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="711db-258">Catalog</span></span>  
  
|<span data-ttu-id="711db-259">ColumnName</span><span class="sxs-lookup"><span data-stu-id="711db-259">ColumnName</span></span>|<span data-ttu-id="711db-260">DataType</span><span class="sxs-lookup"><span data-stu-id="711db-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="711db-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="711db-261">CATALOG_NAME</span></span>|<span data-ttu-id="711db-262">String</span><span class="sxs-lookup"><span data-stu-id="711db-262">String</span></span>|  
|<span data-ttu-id="711db-263">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="711db-263">DESCRIPTION</span></span>|<span data-ttu-id="711db-264">String</span><span class="sxs-lookup"><span data-stu-id="711db-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="711db-265">Индексы</span><span class="sxs-lookup"><span data-stu-id="711db-265">Indexes</span></span>  
  
|<span data-ttu-id="711db-266">ColumnName</span><span class="sxs-lookup"><span data-stu-id="711db-266">ColumnName</span></span>|<span data-ttu-id="711db-267">DataType</span><span class="sxs-lookup"><span data-stu-id="711db-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="711db-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="711db-268">TABLE_CATALOG</span></span>|<span data-ttu-id="711db-269">String</span><span class="sxs-lookup"><span data-stu-id="711db-269">String</span></span>|  
|<span data-ttu-id="711db-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="711db-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="711db-271">String</span><span class="sxs-lookup"><span data-stu-id="711db-271">String</span></span>|  
|<span data-ttu-id="711db-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="711db-272">TABLE_NAME</span></span>|<span data-ttu-id="711db-273">String</span><span class="sxs-lookup"><span data-stu-id="711db-273">String</span></span>|  
|<span data-ttu-id="711db-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="711db-274">INDEX_CATALOG</span></span>|<span data-ttu-id="711db-275">String</span><span class="sxs-lookup"><span data-stu-id="711db-275">String</span></span>|  
|<span data-ttu-id="711db-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="711db-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="711db-277">String</span><span class="sxs-lookup"><span data-stu-id="711db-277">String</span></span>|  
|<span data-ttu-id="711db-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="711db-278">INDEX_NAME</span></span>|<span data-ttu-id="711db-279">String</span><span class="sxs-lookup"><span data-stu-id="711db-279">String</span></span>|  
|<span data-ttu-id="711db-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="711db-280">PRIMARY_KEY</span></span>|<span data-ttu-id="711db-281">Boolean</span><span class="sxs-lookup"><span data-stu-id="711db-281">Boolean</span></span>|  
|<span data-ttu-id="711db-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="711db-282">UNIQUE</span></span>|<span data-ttu-id="711db-283">Boolean</span><span class="sxs-lookup"><span data-stu-id="711db-283">Boolean</span></span>|  
|<span data-ttu-id="711db-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="711db-284">CLUSTERED</span></span>|<span data-ttu-id="711db-285">Boolean</span><span class="sxs-lookup"><span data-stu-id="711db-285">Boolean</span></span>|  
|<span data-ttu-id="711db-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="711db-286">TYPE</span></span>|<span data-ttu-id="711db-287">Int32</span><span class="sxs-lookup"><span data-stu-id="711db-287">Int32</span></span>|  
|<span data-ttu-id="711db-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="711db-288">FILL_FACTOR</span></span>|<span data-ttu-id="711db-289">Int32</span><span class="sxs-lookup"><span data-stu-id="711db-289">Int32</span></span>|  
|<span data-ttu-id="711db-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="711db-290">INITIAL_SIZE</span></span>|<span data-ttu-id="711db-291">Int32</span><span class="sxs-lookup"><span data-stu-id="711db-291">Int32</span></span>|  
|<span data-ttu-id="711db-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="711db-292">NULLS</span></span>|<span data-ttu-id="711db-293">Int32</span><span class="sxs-lookup"><span data-stu-id="711db-293">Int32</span></span>|  
|<span data-ttu-id="711db-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="711db-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="711db-295">Boolean</span><span class="sxs-lookup"><span data-stu-id="711db-295">Boolean</span></span>|  
|<span data-ttu-id="711db-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="711db-296">AUTO_UPDATE</span></span>|<span data-ttu-id="711db-297">Boolean</span><span class="sxs-lookup"><span data-stu-id="711db-297">Boolean</span></span>|  
|<span data-ttu-id="711db-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="711db-298">NULL_COLLATION</span></span>|<span data-ttu-id="711db-299">Int32</span><span class="sxs-lookup"><span data-stu-id="711db-299">Int32</span></span>|  
|<span data-ttu-id="711db-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="711db-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="711db-301">Int64</span><span class="sxs-lookup"><span data-stu-id="711db-301">Int64</span></span>|  
|<span data-ttu-id="711db-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="711db-302">COLUMN_NAME</span></span>|<span data-ttu-id="711db-303">String</span><span class="sxs-lookup"><span data-stu-id="711db-303">String</span></span>|  
|<span data-ttu-id="711db-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="711db-304">COLUMN_GUID</span></span>|<span data-ttu-id="711db-305">Guid</span><span class="sxs-lookup"><span data-stu-id="711db-305">Guid</span></span>|  
|<span data-ttu-id="711db-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="711db-306">COLUMN_PROPID</span></span>|<span data-ttu-id="711db-307">Int64</span><span class="sxs-lookup"><span data-stu-id="711db-307">Int64</span></span>|  
|<span data-ttu-id="711db-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="711db-308">COLLATION</span></span>|<span data-ttu-id="711db-309">Int16</span><span class="sxs-lookup"><span data-stu-id="711db-309">Int16</span></span>|  
|<span data-ttu-id="711db-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="711db-310">CARDINALITY</span></span>|<span data-ttu-id="711db-311">Десятичное число</span><span class="sxs-lookup"><span data-stu-id="711db-311">Decimal</span></span>|  
|<span data-ttu-id="711db-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="711db-312">PAGES</span></span>|<span data-ttu-id="711db-313">Int32</span><span class="sxs-lookup"><span data-stu-id="711db-313">Int32</span></span>|  
|<span data-ttu-id="711db-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="711db-314">FILTER_CONDITION</span></span>|<span data-ttu-id="711db-315">String</span><span class="sxs-lookup"><span data-stu-id="711db-315">String</span></span>|  
|<span data-ttu-id="711db-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="711db-316">INTEGRATED</span></span>|<span data-ttu-id="711db-317">Boolean</span><span class="sxs-lookup"><span data-stu-id="711db-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="711db-318">Поставщик Microsoft OLE DB для Oracle</span><span class="sxs-lookup"><span data-stu-id="711db-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="711db-319">Драйвер OLE DB для Oracle (Майкрософт) поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.</span><span class="sxs-lookup"><span data-stu-id="711db-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="711db-320">Таблицы</span><span class="sxs-lookup"><span data-stu-id="711db-320">Tables</span></span>  
  
- <span data-ttu-id="711db-321">Столбцы</span><span class="sxs-lookup"><span data-stu-id="711db-321">Columns</span></span>  
  
- <span data-ttu-id="711db-322">Процедуры</span><span class="sxs-lookup"><span data-stu-id="711db-322">Procedures</span></span>  
  
- <span data-ttu-id="711db-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="711db-323">ProcedureColumns</span></span>  
  
- <span data-ttu-id="711db-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="711db-324">ProcedureParameters</span></span>  
  
- <span data-ttu-id="711db-325">Представления</span><span class="sxs-lookup"><span data-stu-id="711db-325">Views</span></span>  
  
- <span data-ttu-id="711db-326">Индексы</span><span class="sxs-lookup"><span data-stu-id="711db-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="711db-327">Таблицы</span><span class="sxs-lookup"><span data-stu-id="711db-327">Tables</span></span>  
  
|<span data-ttu-id="711db-328">ColumnName</span><span class="sxs-lookup"><span data-stu-id="711db-328">ColumnName</span></span>|<span data-ttu-id="711db-329">DataType</span><span class="sxs-lookup"><span data-stu-id="711db-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="711db-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="711db-330">TABLE_CATALOG</span></span>|<span data-ttu-id="711db-331">String</span><span class="sxs-lookup"><span data-stu-id="711db-331">String</span></span>|  
|<span data-ttu-id="711db-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="711db-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="711db-333">String</span><span class="sxs-lookup"><span data-stu-id="711db-333">String</span></span>|  
|<span data-ttu-id="711db-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="711db-334">TABLE_NAME</span></span>|<span data-ttu-id="711db-335">String</span><span class="sxs-lookup"><span data-stu-id="711db-335">String</span></span>|  
|<span data-ttu-id="711db-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="711db-336">TABLE_TYPE</span></span>|<span data-ttu-id="711db-337">String</span><span class="sxs-lookup"><span data-stu-id="711db-337">String</span></span>|  
|<span data-ttu-id="711db-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="711db-338">TABLE_GUID</span></span>|<span data-ttu-id="711db-339">Guid</span><span class="sxs-lookup"><span data-stu-id="711db-339">Guid</span></span>|  
|<span data-ttu-id="711db-340">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="711db-340">DESCRIPTION</span></span>|<span data-ttu-id="711db-341">String</span><span class="sxs-lookup"><span data-stu-id="711db-341">String</span></span>|  
|<span data-ttu-id="711db-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="711db-342">TABLE_PROPID</span></span>|<span data-ttu-id="711db-343">Int64</span><span class="sxs-lookup"><span data-stu-id="711db-343">Int64</span></span>|  
|<span data-ttu-id="711db-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="711db-344">DATE_CREATED</span></span>|<span data-ttu-id="711db-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="711db-345">DateTime</span></span>|  
|<span data-ttu-id="711db-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="711db-346">DATE_MODIFIED</span></span>|<span data-ttu-id="711db-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="711db-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="711db-348">Столбцы</span><span class="sxs-lookup"><span data-stu-id="711db-348">Columns</span></span>  
  
|<span data-ttu-id="711db-349">ColumnName</span><span class="sxs-lookup"><span data-stu-id="711db-349">ColumnName</span></span>|<span data-ttu-id="711db-350">DataType</span><span class="sxs-lookup"><span data-stu-id="711db-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="711db-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="711db-351">TABLE_CATALOG</span></span>|<span data-ttu-id="711db-352">String</span><span class="sxs-lookup"><span data-stu-id="711db-352">String</span></span>|  
|<span data-ttu-id="711db-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="711db-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="711db-354">String</span><span class="sxs-lookup"><span data-stu-id="711db-354">String</span></span>|  
|<span data-ttu-id="711db-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="711db-355">TABLE_NAME</span></span>|<span data-ttu-id="711db-356">String</span><span class="sxs-lookup"><span data-stu-id="711db-356">String</span></span>|  
|<span data-ttu-id="711db-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="711db-357">COLUMN_NAME</span></span>|<span data-ttu-id="711db-358">String</span><span class="sxs-lookup"><span data-stu-id="711db-358">String</span></span>|  
|<span data-ttu-id="711db-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="711db-359">COLUMN_GUID</span></span>|<span data-ttu-id="711db-360">Guid</span><span class="sxs-lookup"><span data-stu-id="711db-360">Guid</span></span>|  
|<span data-ttu-id="711db-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="711db-361">COLUMN_PROPID</span></span>|<span data-ttu-id="711db-362">Int64</span><span class="sxs-lookup"><span data-stu-id="711db-362">Int64</span></span>|  
|<span data-ttu-id="711db-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="711db-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="711db-364">Int64</span><span class="sxs-lookup"><span data-stu-id="711db-364">Int64</span></span>|  
|<span data-ttu-id="711db-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="711db-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="711db-366">Boolean</span><span class="sxs-lookup"><span data-stu-id="711db-366">Boolean</span></span>|  
|<span data-ttu-id="711db-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="711db-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="711db-368">String</span><span class="sxs-lookup"><span data-stu-id="711db-368">String</span></span>|  
|<span data-ttu-id="711db-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="711db-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="711db-370">Int64</span><span class="sxs-lookup"><span data-stu-id="711db-370">Int64</span></span>|  
|<span data-ttu-id="711db-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="711db-371">IS_NULLABLE</span></span>|<span data-ttu-id="711db-372">Boolean</span><span class="sxs-lookup"><span data-stu-id="711db-372">Boolean</span></span>|  
|<span data-ttu-id="711db-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="711db-373">DATA_TYPE</span></span>|<span data-ttu-id="711db-374">Int32</span><span class="sxs-lookup"><span data-stu-id="711db-374">Int32</span></span>|  
|<span data-ttu-id="711db-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="711db-375">TYPE_GUID</span></span>|<span data-ttu-id="711db-376">Guid</span><span class="sxs-lookup"><span data-stu-id="711db-376">Guid</span></span>|  
|<span data-ttu-id="711db-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="711db-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="711db-378">Int64</span><span class="sxs-lookup"><span data-stu-id="711db-378">Int64</span></span>|  
|<span data-ttu-id="711db-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="711db-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="711db-380">Int64</span><span class="sxs-lookup"><span data-stu-id="711db-380">Int64</span></span>|  
|<span data-ttu-id="711db-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="711db-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="711db-382">Int32</span><span class="sxs-lookup"><span data-stu-id="711db-382">Int32</span></span>|  
|<span data-ttu-id="711db-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="711db-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="711db-384">Int16</span><span class="sxs-lookup"><span data-stu-id="711db-384">Int16</span></span>|  
|<span data-ttu-id="711db-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="711db-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="711db-386">Int64</span><span class="sxs-lookup"><span data-stu-id="711db-386">Int64</span></span>|  
|<span data-ttu-id="711db-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="711db-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="711db-388">String</span><span class="sxs-lookup"><span data-stu-id="711db-388">String</span></span>|  
|<span data-ttu-id="711db-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="711db-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="711db-390">String</span><span class="sxs-lookup"><span data-stu-id="711db-390">String</span></span>|  
|<span data-ttu-id="711db-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="711db-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="711db-392">String</span><span class="sxs-lookup"><span data-stu-id="711db-392">String</span></span>|  
|<span data-ttu-id="711db-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="711db-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="711db-394">String</span><span class="sxs-lookup"><span data-stu-id="711db-394">String</span></span>|  
|<span data-ttu-id="711db-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="711db-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="711db-396">String</span><span class="sxs-lookup"><span data-stu-id="711db-396">String</span></span>|  
|<span data-ttu-id="711db-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="711db-397">COLLATION_NAME</span></span>|<span data-ttu-id="711db-398">String</span><span class="sxs-lookup"><span data-stu-id="711db-398">String</span></span>|  
|<span data-ttu-id="711db-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="711db-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="711db-400">String</span><span class="sxs-lookup"><span data-stu-id="711db-400">String</span></span>|  
|<span data-ttu-id="711db-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="711db-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="711db-402">String</span><span class="sxs-lookup"><span data-stu-id="711db-402">String</span></span>|  
|<span data-ttu-id="711db-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="711db-403">DOMAIN_NAME</span></span>|<span data-ttu-id="711db-404">String</span><span class="sxs-lookup"><span data-stu-id="711db-404">String</span></span>|  
|<span data-ttu-id="711db-405">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="711db-405">DESCRIPTION</span></span>|<span data-ttu-id="711db-406">String</span><span class="sxs-lookup"><span data-stu-id="711db-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="711db-407">Процедуры</span><span class="sxs-lookup"><span data-stu-id="711db-407">Procedures</span></span>  
  
|<span data-ttu-id="711db-408">ColumnName</span><span class="sxs-lookup"><span data-stu-id="711db-408">ColumnName</span></span>|<span data-ttu-id="711db-409">DataType</span><span class="sxs-lookup"><span data-stu-id="711db-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="711db-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="711db-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="711db-411">String</span><span class="sxs-lookup"><span data-stu-id="711db-411">String</span></span>|  
|<span data-ttu-id="711db-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="711db-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="711db-413">String</span><span class="sxs-lookup"><span data-stu-id="711db-413">String</span></span>|  
|<span data-ttu-id="711db-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="711db-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="711db-415">String</span><span class="sxs-lookup"><span data-stu-id="711db-415">String</span></span>|  
|<span data-ttu-id="711db-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="711db-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="711db-417">Int16</span><span class="sxs-lookup"><span data-stu-id="711db-417">Int16</span></span>|  
|<span data-ttu-id="711db-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="711db-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="711db-419">String</span><span class="sxs-lookup"><span data-stu-id="711db-419">String</span></span>|  
|<span data-ttu-id="711db-420">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="711db-420">DESCRIPTION</span></span>|<span data-ttu-id="711db-421">String</span><span class="sxs-lookup"><span data-stu-id="711db-421">String</span></span>|  
|<span data-ttu-id="711db-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="711db-422">DATE_CREATED</span></span>|<span data-ttu-id="711db-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="711db-423">DateTime</span></span>|  
|<span data-ttu-id="711db-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="711db-424">DATE_MODIFIED</span></span>|<span data-ttu-id="711db-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="711db-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="711db-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="711db-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="711db-427">ColumnName</span><span class="sxs-lookup"><span data-stu-id="711db-427">ColumnName</span></span>|<span data-ttu-id="711db-428">DataType</span><span class="sxs-lookup"><span data-stu-id="711db-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="711db-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="711db-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="711db-430">String</span><span class="sxs-lookup"><span data-stu-id="711db-430">String</span></span>|  
|<span data-ttu-id="711db-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="711db-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="711db-432">String</span><span class="sxs-lookup"><span data-stu-id="711db-432">String</span></span>|  
|<span data-ttu-id="711db-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="711db-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="711db-434">String</span><span class="sxs-lookup"><span data-stu-id="711db-434">String</span></span>|  
|<span data-ttu-id="711db-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="711db-435">COLUMN_NAME</span></span>|<span data-ttu-id="711db-436">String</span><span class="sxs-lookup"><span data-stu-id="711db-436">String</span></span>|  
|<span data-ttu-id="711db-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="711db-437">COLUMN_GUID</span></span>|<span data-ttu-id="711db-438">Guid</span><span class="sxs-lookup"><span data-stu-id="711db-438">Guid</span></span>|  
|<span data-ttu-id="711db-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="711db-439">COLUMN_PROPID</span></span>|<span data-ttu-id="711db-440">Int64</span><span class="sxs-lookup"><span data-stu-id="711db-440">Int64</span></span>|  
|<span data-ttu-id="711db-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="711db-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="711db-442">Int64</span><span class="sxs-lookup"><span data-stu-id="711db-442">Int64</span></span>|  
|<span data-ttu-id="711db-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="711db-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="711db-444">Int64</span><span class="sxs-lookup"><span data-stu-id="711db-444">Int64</span></span>|  
|<span data-ttu-id="711db-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="711db-445">IS_NULLABLE</span></span>|<span data-ttu-id="711db-446">Boolean</span><span class="sxs-lookup"><span data-stu-id="711db-446">Boolean</span></span>|  
|<span data-ttu-id="711db-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="711db-447">DATA_TYPE</span></span>|<span data-ttu-id="711db-448">Int32</span><span class="sxs-lookup"><span data-stu-id="711db-448">Int32</span></span>|  
|<span data-ttu-id="711db-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="711db-449">TYPE_GUID</span></span>|<span data-ttu-id="711db-450">Guid</span><span class="sxs-lookup"><span data-stu-id="711db-450">Guid</span></span>|  
|<span data-ttu-id="711db-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="711db-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="711db-452">Int64</span><span class="sxs-lookup"><span data-stu-id="711db-452">Int64</span></span>|  
|<span data-ttu-id="711db-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="711db-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="711db-454">Int64</span><span class="sxs-lookup"><span data-stu-id="711db-454">Int64</span></span>|  
|<span data-ttu-id="711db-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="711db-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="711db-456">Int32</span><span class="sxs-lookup"><span data-stu-id="711db-456">Int32</span></span>|  
|<span data-ttu-id="711db-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="711db-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="711db-458">Int16</span><span class="sxs-lookup"><span data-stu-id="711db-458">Int16</span></span>|  
|<span data-ttu-id="711db-459">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="711db-459">DESCRIPTION</span></span>|<span data-ttu-id="711db-460">String</span><span class="sxs-lookup"><span data-stu-id="711db-460">String</span></span>|  
|<span data-ttu-id="711db-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="711db-461">OVERLOAD</span></span>|<span data-ttu-id="711db-462">Int16</span><span class="sxs-lookup"><span data-stu-id="711db-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="711db-463">Представления</span><span class="sxs-lookup"><span data-stu-id="711db-463">Views</span></span>  
  
|<span data-ttu-id="711db-464">ColumnName</span><span class="sxs-lookup"><span data-stu-id="711db-464">ColumnName</span></span>|<span data-ttu-id="711db-465">DataType</span><span class="sxs-lookup"><span data-stu-id="711db-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="711db-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="711db-466">TABLE_CATALOG</span></span>|<span data-ttu-id="711db-467">String</span><span class="sxs-lookup"><span data-stu-id="711db-467">String</span></span>|  
|<span data-ttu-id="711db-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="711db-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="711db-469">String</span><span class="sxs-lookup"><span data-stu-id="711db-469">String</span></span>|  
|<span data-ttu-id="711db-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="711db-470">TABLE_NAME</span></span>|<span data-ttu-id="711db-471">String</span><span class="sxs-lookup"><span data-stu-id="711db-471">String</span></span>|  
|<span data-ttu-id="711db-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="711db-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="711db-473">String</span><span class="sxs-lookup"><span data-stu-id="711db-473">String</span></span>|  
|<span data-ttu-id="711db-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="711db-474">CHECK_OPTION</span></span>|<span data-ttu-id="711db-475">Boolean</span><span class="sxs-lookup"><span data-stu-id="711db-475">Boolean</span></span>|  
|<span data-ttu-id="711db-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="711db-476">IS_UPDATABLE</span></span>|<span data-ttu-id="711db-477">Boolean</span><span class="sxs-lookup"><span data-stu-id="711db-477">Boolean</span></span>|  
|<span data-ttu-id="711db-478">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="711db-478">DESCRIPTION</span></span>|<span data-ttu-id="711db-479">String</span><span class="sxs-lookup"><span data-stu-id="711db-479">String</span></span>|  
|<span data-ttu-id="711db-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="711db-480">DATE_CREATED</span></span>|<span data-ttu-id="711db-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="711db-481">DateTime</span></span>|  
|<span data-ttu-id="711db-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="711db-482">DATE_MODIFIED</span></span>|<span data-ttu-id="711db-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="711db-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="711db-484">Индексы</span><span class="sxs-lookup"><span data-stu-id="711db-484">Indexes</span></span>  
  
|<span data-ttu-id="711db-485">ColumnName</span><span class="sxs-lookup"><span data-stu-id="711db-485">ColumnName</span></span>|<span data-ttu-id="711db-486">DataType</span><span class="sxs-lookup"><span data-stu-id="711db-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="711db-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="711db-487">TABLE_CATALOG</span></span>|<span data-ttu-id="711db-488">String</span><span class="sxs-lookup"><span data-stu-id="711db-488">String</span></span>|  
|<span data-ttu-id="711db-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="711db-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="711db-490">String</span><span class="sxs-lookup"><span data-stu-id="711db-490">String</span></span>|  
|<span data-ttu-id="711db-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="711db-491">TABLE_NAME</span></span>|<span data-ttu-id="711db-492">String</span><span class="sxs-lookup"><span data-stu-id="711db-492">String</span></span>|  
|<span data-ttu-id="711db-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="711db-493">INDEX_CATALOG</span></span>|<span data-ttu-id="711db-494">String</span><span class="sxs-lookup"><span data-stu-id="711db-494">String</span></span>|  
|<span data-ttu-id="711db-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="711db-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="711db-496">String</span><span class="sxs-lookup"><span data-stu-id="711db-496">String</span></span>|  
|<span data-ttu-id="711db-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="711db-497">INDEX_NAME</span></span>|<span data-ttu-id="711db-498">String</span><span class="sxs-lookup"><span data-stu-id="711db-498">String</span></span>|  
|<span data-ttu-id="711db-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="711db-499">PRIMARY_KEY</span></span>|<span data-ttu-id="711db-500">Boolean</span><span class="sxs-lookup"><span data-stu-id="711db-500">Boolean</span></span>|  
|<span data-ttu-id="711db-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="711db-501">UNIQUE</span></span>|<span data-ttu-id="711db-502">Boolean</span><span class="sxs-lookup"><span data-stu-id="711db-502">Boolean</span></span>|  
|<span data-ttu-id="711db-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="711db-503">CLUSTERED</span></span>|<span data-ttu-id="711db-504">Boolean</span><span class="sxs-lookup"><span data-stu-id="711db-504">Boolean</span></span>|  
|<span data-ttu-id="711db-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="711db-505">TYPE</span></span>|<span data-ttu-id="711db-506">Int32</span><span class="sxs-lookup"><span data-stu-id="711db-506">Int32</span></span>|  
|<span data-ttu-id="711db-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="711db-507">FILL_FACTOR</span></span>|<span data-ttu-id="711db-508">Int32</span><span class="sxs-lookup"><span data-stu-id="711db-508">Int32</span></span>|  
|<span data-ttu-id="711db-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="711db-509">INITIAL_SIZE</span></span>|<span data-ttu-id="711db-510">Int32</span><span class="sxs-lookup"><span data-stu-id="711db-510">Int32</span></span>|  
|<span data-ttu-id="711db-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="711db-511">NULLS</span></span>|<span data-ttu-id="711db-512">Int32</span><span class="sxs-lookup"><span data-stu-id="711db-512">Int32</span></span>|  
|<span data-ttu-id="711db-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="711db-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="711db-514">Boolean</span><span class="sxs-lookup"><span data-stu-id="711db-514">Boolean</span></span>|  
|<span data-ttu-id="711db-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="711db-515">AUTO_UPDATE</span></span>|<span data-ttu-id="711db-516">Boolean</span><span class="sxs-lookup"><span data-stu-id="711db-516">Boolean</span></span>|  
|<span data-ttu-id="711db-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="711db-517">NULL_COLLATION</span></span>|<span data-ttu-id="711db-518">Int32</span><span class="sxs-lookup"><span data-stu-id="711db-518">Int32</span></span>|  
|<span data-ttu-id="711db-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="711db-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="711db-520">Int64</span><span class="sxs-lookup"><span data-stu-id="711db-520">Int64</span></span>|  
|<span data-ttu-id="711db-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="711db-521">COLUMN_NAME</span></span>|<span data-ttu-id="711db-522">String</span><span class="sxs-lookup"><span data-stu-id="711db-522">String</span></span>|  
|<span data-ttu-id="711db-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="711db-523">COLUMN_GUID</span></span>|<span data-ttu-id="711db-524">Guid</span><span class="sxs-lookup"><span data-stu-id="711db-524">Guid</span></span>|  
|<span data-ttu-id="711db-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="711db-525">COLUMN_PROPID</span></span>|<span data-ttu-id="711db-526">Int64</span><span class="sxs-lookup"><span data-stu-id="711db-526">Int64</span></span>|  
|<span data-ttu-id="711db-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="711db-527">COLLATION</span></span>|<span data-ttu-id="711db-528">Int16</span><span class="sxs-lookup"><span data-stu-id="711db-528">Int16</span></span>|  
|<span data-ttu-id="711db-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="711db-529">CARDINALITY</span></span>|<span data-ttu-id="711db-530">Десятичное число</span><span class="sxs-lookup"><span data-stu-id="711db-530">Decimal</span></span>|  
|<span data-ttu-id="711db-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="711db-531">PAGES</span></span>|<span data-ttu-id="711db-532">Int32</span><span class="sxs-lookup"><span data-stu-id="711db-532">Int32</span></span>|  
|<span data-ttu-id="711db-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="711db-533">FILTER_CONDITION</span></span>|<span data-ttu-id="711db-534">String</span><span class="sxs-lookup"><span data-stu-id="711db-534">String</span></span>|  
|<span data-ttu-id="711db-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="711db-535">INTEGRATED</span></span>|<span data-ttu-id="711db-536">Boolean</span><span class="sxs-lookup"><span data-stu-id="711db-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="711db-537">Поставщик OLE DB для Microsoft Jet</span><span class="sxs-lookup"><span data-stu-id="711db-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="711db-538">Драйвер OLE DB для Jet (Майкрософт) поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.</span><span class="sxs-lookup"><span data-stu-id="711db-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="711db-539">Таблицы</span><span class="sxs-lookup"><span data-stu-id="711db-539">Tables</span></span>  
  
- <span data-ttu-id="711db-540">Столбцы</span><span class="sxs-lookup"><span data-stu-id="711db-540">Columns</span></span>  
  
- <span data-ttu-id="711db-541">Процедуры</span><span class="sxs-lookup"><span data-stu-id="711db-541">Procedures</span></span>  
  
- <span data-ttu-id="711db-542">Представления</span><span class="sxs-lookup"><span data-stu-id="711db-542">Views</span></span>  
  
- <span data-ttu-id="711db-543">Индексы</span><span class="sxs-lookup"><span data-stu-id="711db-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="711db-544">Таблицы</span><span class="sxs-lookup"><span data-stu-id="711db-544">Tables</span></span>  
  
|<span data-ttu-id="711db-545">ColumnName</span><span class="sxs-lookup"><span data-stu-id="711db-545">ColumnName</span></span>|<span data-ttu-id="711db-546">DataType</span><span class="sxs-lookup"><span data-stu-id="711db-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="711db-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="711db-547">TABLE_CATALOG</span></span>|<span data-ttu-id="711db-548">String</span><span class="sxs-lookup"><span data-stu-id="711db-548">String</span></span>|  
|<span data-ttu-id="711db-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="711db-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="711db-550">String</span><span class="sxs-lookup"><span data-stu-id="711db-550">String</span></span>|  
|<span data-ttu-id="711db-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="711db-551">TABLE_NAME</span></span>|<span data-ttu-id="711db-552">String</span><span class="sxs-lookup"><span data-stu-id="711db-552">String</span></span>|  
|<span data-ttu-id="711db-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="711db-553">TABLE_TYPE</span></span>|<span data-ttu-id="711db-554">String</span><span class="sxs-lookup"><span data-stu-id="711db-554">String</span></span>|  
|<span data-ttu-id="711db-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="711db-555">TABLE_GUID</span></span>|<span data-ttu-id="711db-556">Guid</span><span class="sxs-lookup"><span data-stu-id="711db-556">Guid</span></span>|  
|<span data-ttu-id="711db-557">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="711db-557">DESCRIPTION</span></span>|<span data-ttu-id="711db-558">String</span><span class="sxs-lookup"><span data-stu-id="711db-558">String</span></span>|  
|<span data-ttu-id="711db-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="711db-559">TABLE_PROPID</span></span>|<span data-ttu-id="711db-560">Int64</span><span class="sxs-lookup"><span data-stu-id="711db-560">Int64</span></span>|  
|<span data-ttu-id="711db-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="711db-561">DATE_CREATED</span></span>|<span data-ttu-id="711db-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="711db-562">DateTime</span></span>|  
|<span data-ttu-id="711db-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="711db-563">DATE_MODIFIED</span></span>|<span data-ttu-id="711db-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="711db-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="711db-565">Столбцы</span><span class="sxs-lookup"><span data-stu-id="711db-565">Columns</span></span>  
  
|<span data-ttu-id="711db-566">ColumnName</span><span class="sxs-lookup"><span data-stu-id="711db-566">ColumnName</span></span>|<span data-ttu-id="711db-567">DataType</span><span class="sxs-lookup"><span data-stu-id="711db-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="711db-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="711db-568">TABLE_CATALOG</span></span>|<span data-ttu-id="711db-569">String</span><span class="sxs-lookup"><span data-stu-id="711db-569">String</span></span>|  
|<span data-ttu-id="711db-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="711db-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="711db-571">String</span><span class="sxs-lookup"><span data-stu-id="711db-571">String</span></span>|  
|<span data-ttu-id="711db-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="711db-572">TABLE_NAME</span></span>|<span data-ttu-id="711db-573">String</span><span class="sxs-lookup"><span data-stu-id="711db-573">String</span></span>|  
|<span data-ttu-id="711db-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="711db-574">COLUMN_NAME</span></span>|<span data-ttu-id="711db-575">String</span><span class="sxs-lookup"><span data-stu-id="711db-575">String</span></span>|  
|<span data-ttu-id="711db-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="711db-576">COLUMN_GUID</span></span>|<span data-ttu-id="711db-577">Guid</span><span class="sxs-lookup"><span data-stu-id="711db-577">Guid</span></span>|  
|<span data-ttu-id="711db-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="711db-578">COLUMN_PROPID</span></span>|<span data-ttu-id="711db-579">Int64</span><span class="sxs-lookup"><span data-stu-id="711db-579">Int64</span></span>|  
|<span data-ttu-id="711db-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="711db-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="711db-581">Int64</span><span class="sxs-lookup"><span data-stu-id="711db-581">Int64</span></span>|  
|<span data-ttu-id="711db-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="711db-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="711db-583">Boolean</span><span class="sxs-lookup"><span data-stu-id="711db-583">Boolean</span></span>|  
|<span data-ttu-id="711db-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="711db-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="711db-585">String</span><span class="sxs-lookup"><span data-stu-id="711db-585">String</span></span>|  
|<span data-ttu-id="711db-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="711db-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="711db-587">Int64</span><span class="sxs-lookup"><span data-stu-id="711db-587">Int64</span></span>|  
|<span data-ttu-id="711db-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="711db-588">IS_NULLABLE</span></span>|<span data-ttu-id="711db-589">Boolean</span><span class="sxs-lookup"><span data-stu-id="711db-589">Boolean</span></span>|  
|<span data-ttu-id="711db-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="711db-590">DATA_TYPE</span></span>|<span data-ttu-id="711db-591">Int32</span><span class="sxs-lookup"><span data-stu-id="711db-591">Int32</span></span>|  
|<span data-ttu-id="711db-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="711db-592">TYPE_GUID</span></span>|<span data-ttu-id="711db-593">Guid</span><span class="sxs-lookup"><span data-stu-id="711db-593">Guid</span></span>|  
|<span data-ttu-id="711db-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="711db-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="711db-595">Int64</span><span class="sxs-lookup"><span data-stu-id="711db-595">Int64</span></span>|  
|<span data-ttu-id="711db-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="711db-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="711db-597">Int64</span><span class="sxs-lookup"><span data-stu-id="711db-597">Int64</span></span>|  
|<span data-ttu-id="711db-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="711db-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="711db-599">Int32</span><span class="sxs-lookup"><span data-stu-id="711db-599">Int32</span></span>|  
|<span data-ttu-id="711db-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="711db-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="711db-601">Int16</span><span class="sxs-lookup"><span data-stu-id="711db-601">Int16</span></span>|  
|<span data-ttu-id="711db-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="711db-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="711db-603">Int64</span><span class="sxs-lookup"><span data-stu-id="711db-603">Int64</span></span>|  
|<span data-ttu-id="711db-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="711db-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="711db-605">String</span><span class="sxs-lookup"><span data-stu-id="711db-605">String</span></span>|  
|<span data-ttu-id="711db-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="711db-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="711db-607">String</span><span class="sxs-lookup"><span data-stu-id="711db-607">String</span></span>|  
|<span data-ttu-id="711db-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="711db-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="711db-609">String</span><span class="sxs-lookup"><span data-stu-id="711db-609">String</span></span>|  
|<span data-ttu-id="711db-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="711db-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="711db-611">String</span><span class="sxs-lookup"><span data-stu-id="711db-611">String</span></span>|  
|<span data-ttu-id="711db-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="711db-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="711db-613">String</span><span class="sxs-lookup"><span data-stu-id="711db-613">String</span></span>|  
|<span data-ttu-id="711db-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="711db-614">COLLATION_NAME</span></span>|<span data-ttu-id="711db-615">String</span><span class="sxs-lookup"><span data-stu-id="711db-615">String</span></span>|  
|<span data-ttu-id="711db-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="711db-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="711db-617">String</span><span class="sxs-lookup"><span data-stu-id="711db-617">String</span></span>|  
|<span data-ttu-id="711db-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="711db-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="711db-619">String</span><span class="sxs-lookup"><span data-stu-id="711db-619">String</span></span>|  
|<span data-ttu-id="711db-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="711db-620">DOMAIN_NAME</span></span>|<span data-ttu-id="711db-621">String</span><span class="sxs-lookup"><span data-stu-id="711db-621">String</span></span>|  
|<span data-ttu-id="711db-622">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="711db-622">DESCRIPTION</span></span>|<span data-ttu-id="711db-623">String</span><span class="sxs-lookup"><span data-stu-id="711db-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="711db-624">Процедуры</span><span class="sxs-lookup"><span data-stu-id="711db-624">Procedures</span></span>  
  
|<span data-ttu-id="711db-625">ColumnName</span><span class="sxs-lookup"><span data-stu-id="711db-625">ColumnName</span></span>|<span data-ttu-id="711db-626">DataType</span><span class="sxs-lookup"><span data-stu-id="711db-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="711db-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="711db-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="711db-628">String</span><span class="sxs-lookup"><span data-stu-id="711db-628">String</span></span>|  
|<span data-ttu-id="711db-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="711db-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="711db-630">String</span><span class="sxs-lookup"><span data-stu-id="711db-630">String</span></span>|  
|<span data-ttu-id="711db-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="711db-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="711db-632">String</span><span class="sxs-lookup"><span data-stu-id="711db-632">String</span></span>|  
|<span data-ttu-id="711db-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="711db-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="711db-634">Int16</span><span class="sxs-lookup"><span data-stu-id="711db-634">Int16</span></span>|  
|<span data-ttu-id="711db-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="711db-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="711db-636">String</span><span class="sxs-lookup"><span data-stu-id="711db-636">String</span></span>|  
|<span data-ttu-id="711db-637">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="711db-637">DESCRIPTION</span></span>|<span data-ttu-id="711db-638">String</span><span class="sxs-lookup"><span data-stu-id="711db-638">String</span></span>|  
|<span data-ttu-id="711db-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="711db-639">DATE_CREATED</span></span>|<span data-ttu-id="711db-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="711db-640">DateTime</span></span>|  
|<span data-ttu-id="711db-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="711db-641">DATE_MODIFIED</span></span>|<span data-ttu-id="711db-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="711db-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="711db-643">Представления</span><span class="sxs-lookup"><span data-stu-id="711db-643">Views</span></span>  
  
|<span data-ttu-id="711db-644">ColumnName</span><span class="sxs-lookup"><span data-stu-id="711db-644">ColumnName</span></span>|<span data-ttu-id="711db-645">DataType</span><span class="sxs-lookup"><span data-stu-id="711db-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="711db-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="711db-646">TABLE_CATALOG</span></span>|<span data-ttu-id="711db-647">String</span><span class="sxs-lookup"><span data-stu-id="711db-647">String</span></span>|  
|<span data-ttu-id="711db-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="711db-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="711db-649">String</span><span class="sxs-lookup"><span data-stu-id="711db-649">String</span></span>|  
|<span data-ttu-id="711db-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="711db-650">TABLE_NAME</span></span>|<span data-ttu-id="711db-651">String</span><span class="sxs-lookup"><span data-stu-id="711db-651">String</span></span>|  
|<span data-ttu-id="711db-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="711db-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="711db-653">String</span><span class="sxs-lookup"><span data-stu-id="711db-653">String</span></span>|  
|<span data-ttu-id="711db-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="711db-654">CHECK_OPTION</span></span>|<span data-ttu-id="711db-655">Boolean</span><span class="sxs-lookup"><span data-stu-id="711db-655">Boolean</span></span>|  
|<span data-ttu-id="711db-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="711db-656">IS_UPDATABLE</span></span>|<span data-ttu-id="711db-657">Boolean</span><span class="sxs-lookup"><span data-stu-id="711db-657">Boolean</span></span>|  
|<span data-ttu-id="711db-658">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="711db-658">DESCRIPTION</span></span>|<span data-ttu-id="711db-659">String</span><span class="sxs-lookup"><span data-stu-id="711db-659">String</span></span>|  
|<span data-ttu-id="711db-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="711db-660">DATE_CREATED</span></span>|<span data-ttu-id="711db-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="711db-661">DateTime</span></span>|  
|<span data-ttu-id="711db-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="711db-662">DATE_MODIFIED</span></span>|<span data-ttu-id="711db-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="711db-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="711db-664">Индексы</span><span class="sxs-lookup"><span data-stu-id="711db-664">Indexes</span></span>  
  
|<span data-ttu-id="711db-665">ColumnName</span><span class="sxs-lookup"><span data-stu-id="711db-665">ColumnName</span></span>|<span data-ttu-id="711db-666">DataType</span><span class="sxs-lookup"><span data-stu-id="711db-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="711db-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="711db-667">TABLE_CATALOG</span></span>|<span data-ttu-id="711db-668">String</span><span class="sxs-lookup"><span data-stu-id="711db-668">String</span></span>|  
|<span data-ttu-id="711db-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="711db-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="711db-670">String</span><span class="sxs-lookup"><span data-stu-id="711db-670">String</span></span>|  
|<span data-ttu-id="711db-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="711db-671">TABLE_NAME</span></span>|<span data-ttu-id="711db-672">String</span><span class="sxs-lookup"><span data-stu-id="711db-672">String</span></span>|  
|<span data-ttu-id="711db-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="711db-673">INDEX_CATALOG</span></span>|<span data-ttu-id="711db-674">String</span><span class="sxs-lookup"><span data-stu-id="711db-674">String</span></span>|  
|<span data-ttu-id="711db-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="711db-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="711db-676">String</span><span class="sxs-lookup"><span data-stu-id="711db-676">String</span></span>|  
|<span data-ttu-id="711db-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="711db-677">INDEX_NAME</span></span>|<span data-ttu-id="711db-678">String</span><span class="sxs-lookup"><span data-stu-id="711db-678">String</span></span>|  
|<span data-ttu-id="711db-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="711db-679">PRIMARY_KEY</span></span>|<span data-ttu-id="711db-680">Boolean</span><span class="sxs-lookup"><span data-stu-id="711db-680">Boolean</span></span>|  
|<span data-ttu-id="711db-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="711db-681">UNIQUE</span></span>|<span data-ttu-id="711db-682">Boolean</span><span class="sxs-lookup"><span data-stu-id="711db-682">Boolean</span></span>|  
|<span data-ttu-id="711db-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="711db-683">CLUSTERED</span></span>|<span data-ttu-id="711db-684">Boolean</span><span class="sxs-lookup"><span data-stu-id="711db-684">Boolean</span></span>|  
|<span data-ttu-id="711db-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="711db-685">TYPE</span></span>|<span data-ttu-id="711db-686">Int32</span><span class="sxs-lookup"><span data-stu-id="711db-686">Int32</span></span>|  
|<span data-ttu-id="711db-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="711db-687">FILL_FACTOR</span></span>|<span data-ttu-id="711db-688">Int32</span><span class="sxs-lookup"><span data-stu-id="711db-688">Int32</span></span>|  
|<span data-ttu-id="711db-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="711db-689">INITIAL_SIZE</span></span>|<span data-ttu-id="711db-690">Int32</span><span class="sxs-lookup"><span data-stu-id="711db-690">Int32</span></span>|  
|<span data-ttu-id="711db-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="711db-691">NULLS</span></span>|<span data-ttu-id="711db-692">Int32</span><span class="sxs-lookup"><span data-stu-id="711db-692">Int32</span></span>|  
|<span data-ttu-id="711db-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="711db-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="711db-694">Boolean</span><span class="sxs-lookup"><span data-stu-id="711db-694">Boolean</span></span>|  
|<span data-ttu-id="711db-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="711db-695">AUTO_UPDATE</span></span>|<span data-ttu-id="711db-696">Boolean</span><span class="sxs-lookup"><span data-stu-id="711db-696">Boolean</span></span>|  
|<span data-ttu-id="711db-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="711db-697">NULL_COLLATION</span></span>|<span data-ttu-id="711db-698">Int32</span><span class="sxs-lookup"><span data-stu-id="711db-698">Int32</span></span>|  
|<span data-ttu-id="711db-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="711db-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="711db-700">Int64</span><span class="sxs-lookup"><span data-stu-id="711db-700">Int64</span></span>|  
|<span data-ttu-id="711db-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="711db-701">COLUMN_NAME</span></span>|<span data-ttu-id="711db-702">String</span><span class="sxs-lookup"><span data-stu-id="711db-702">String</span></span>|  
|<span data-ttu-id="711db-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="711db-703">COLUMN_GUID</span></span>|<span data-ttu-id="711db-704">Guid</span><span class="sxs-lookup"><span data-stu-id="711db-704">Guid</span></span>|  
|<span data-ttu-id="711db-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="711db-705">COLUMN_PROPID</span></span>|<span data-ttu-id="711db-706">Int64</span><span class="sxs-lookup"><span data-stu-id="711db-706">Int64</span></span>|  
|<span data-ttu-id="711db-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="711db-707">COLLATION</span></span>|<span data-ttu-id="711db-708">Int16</span><span class="sxs-lookup"><span data-stu-id="711db-708">Int16</span></span>|  
|<span data-ttu-id="711db-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="711db-709">CARDINALITY</span></span>|<span data-ttu-id="711db-710">Десятичное число</span><span class="sxs-lookup"><span data-stu-id="711db-710">Decimal</span></span>|  
|<span data-ttu-id="711db-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="711db-711">PAGES</span></span>|<span data-ttu-id="711db-712">Int32</span><span class="sxs-lookup"><span data-stu-id="711db-712">Int32</span></span>|  
|<span data-ttu-id="711db-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="711db-713">FILTER_CONDITION</span></span>|<span data-ttu-id="711db-714">String</span><span class="sxs-lookup"><span data-stu-id="711db-714">String</span></span>|  
|<span data-ttu-id="711db-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="711db-715">INTEGRATED</span></span>|<span data-ttu-id="711db-716">Boolean</span><span class="sxs-lookup"><span data-stu-id="711db-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="711db-717">См. также</span><span class="sxs-lookup"><span data-stu-id="711db-717">See also</span></span>

- [<span data-ttu-id="711db-718">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="711db-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
