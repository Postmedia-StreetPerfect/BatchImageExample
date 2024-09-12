FROM public.ecr.aws/postmedia/streetperfect/sp-poc-batch-public as base

# a volume we expect the input file and ini file located
# the cloud framework needs to map this volume to an external filesystem (like EFS in AWS)
VOLUME /spdata


ENTRYPOINT ["/app/bin/StreetPerfectPocBatchDriver", "/spdata/MyDockerSpPoc.ini"]
