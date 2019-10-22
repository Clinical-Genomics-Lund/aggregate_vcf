## Aggregate VCFs

Requires vcf-module /data/bnf/scripts/CMD/vcf.pm

To run the script

`nextflow run main.nf --csv input.csv -with-singularity /fs1/resources/containers/container_twist-brca.sif -resume --reads 1,1,0 --manta --melt`



aggregate_vcf.pl --base BASE_VARIANT_CALLER [--freebayes/mutect/pindel/vardict/gatkhc/manta/strelka VCF [--fluffify-pindel] [--tumor-id --normal-id]
   --base        Defines which variant caller is used as base vcf (required)

    Any number of these are allowed, at least one required:
    --freebayes VCF   Freebayes VCF path
    --vardict VCF     VarDict VCF path
    --mutect VCF      MuTect2 VCF path
    --manta VCF       Manta VCF path
    --pindel VCF      pindel VCF path
    --strelka VCF     Strelka2 VCF path
	--tnscope VCF     Tnscope VCF path
    --gatkhc VCF      GATK HaplotypeCaller VCF path

    Additional options:
    --fluffify-pindel Modify pindel REF/ALT fields to be less than 1000 bp (comply with Manta).
    --tumor-id STR    REQUIRED IFF STRELKA: Sample ID for for tumor sample
    --normal-id STR   REQUIRED IFF STRELKA: Sample ID for for normal sample


## Known Issues