# 📢🚨📣 `Sciscinet-v2`
`Sciscinet-v2` is a refreshed update to [SciSciNet](https://doi.org/10.1038/s41597-023-02198-9) which is a large-scale, integrated dataset designed to support research in the science of science domain. It combines scientific publications with their network of relationships to funding sources, patents, citations, and institutional affiliations, creating a rich ecosystem for analyzing scientific productivity, impact, and innovation. [Know more](https://northwestern-cssi.github.io/sciscinet/).

<img src="https://github.com/Northwestern-CSSI/sciscinet/blob/main/media/twt-image-1.png?raw=true" width="400">

### About `Sciscinet-v2`
The newer version `Sciscinet-v2` is rebuilt using the latest snapshot from [OpenAlex](https://docs.openalex.org/). Here are some informative comparisons of `Sciscinet-v2` with `Sciscinet-v1`.

<img src="https://github.com/Northwestern-CSSI/sciscinet/blob/main/media/twt-image-2.png?raw=true" width="400">

### FAQ about `Sciscinet-v2`
1. How does Sciscinet-v2 compare to the previous version ?
<img src="https://github.com/Northwestern-CSSI/sciscinet/blob/main/media/twt-image-4.png?raw=true" width="400">
<img src="https://github.com/Northwestern-CSSI/sciscinet/blob/main/media/twt-image-5.png?raw=true" width="400">

2. Does Sciscinet-v2 include precomputed metrics and linkages ?
<img src="https://github.com/Northwestern-CSSI/sciscinet/blob/main/media/twt-image-7.png?raw=true" width="400">
<img src="https://github.com/Northwestern-CSSI/sciscinet/blob/main/media/twt-image-6.png?raw=true" width="400">

3. Do you have precomputed embeddings for papers ?
<img src="https://github.com/Northwestern-CSSI/sciscinet/blob/main/media/twt-image-8.png?raw=true" width="400">
Due to the sheer size of the embeddings (1.7TB), the chunked embeddings are hosted on Google cloud storage.
The easiest way to access them through the following command:

```shell
$ gsutil -m cp -r gs://sciscinet-neo/v2/embeddings/* ./path/to/your/directory/
```

**4. I donot see `sciscinet_paperdetails.parquet` or `sciscinet_papertitleabstract.parquet` on Huggingface, where can i find them ?**

`sciscinet_paperdetails.parquet` (117 GB) and `sciscinet_papertitleabstract.parquet` (92GB) are hosted on Google cloud storage and Big Query
exclusively because of the size of the files. You can simply access them using the command

```shell
$ gsutil ls gs://sciscinet-neo/v2 | grep -e "sciscinet_paperdetails"
gs://sciscinet-neo/v2/sciscinet_paperdetails.parquet

$ gsutil ls gs://sciscinet-neo/v2 | grep -e "sciscinet_papertitleabstract"
gs://sciscinet-neo/v2/sciscinet_papertitleabstract.parquet
```

**5. I donot see `sciscinet_journals` similar to v1, where can i find journal information ?**

Since `Sciscinet-v2` is built on top of [OpenAlex](https://docs.openalex.org/), journal information is stored in the form of [Sources](https://docs.openalex.org/api-entities/sources).
You can find the same dynamic in the file `sciscinet_sources.parquet` and paper-source mapping in `sciscinet_papersources.parquet`.

### Access `Sciscinet-v2`
<img src="https://github.com/Northwestern-CSSI/sciscinet/blob/main/media/twt-image-9.png?raw=true" width="400">

More information can be found on https://northwestern-cssi.github.io/sciscinet/.

<hr>

For more information about the previous [Sciscinet-v1] version visit [README_OLD.md](./README_OLD.md).
