# Arcaflow MinIO Plugin

The MinIO plugin creates an ephemeral object store that can be used during the operation of a workflow. A single `arca-bucket` storage bucket is created, and the plugin returns in its output object the required credentials for accessing the bucket.

## Accessing the bucket

In order to access the bucket, the MinIO plugin container will need to be launched with internal port 9000 exposed.

The MinIO object store is S3 compatible, so it is possible to use the S3 libraries, the simpler MinIO libraries (recommended), or any other S3 compatible client methods to access the bucket.

The MinIO server is run as **insecure** so connections are via HTTP without certificates.

## Persistent storage

If you would like for your bucket contents to survive after the workflow execution, you will need to mount a persistent filesystem to the container at `/mnt/arca-bucket`. You will then be able to run a MinIO server separately using this storage location and re-establish access to the bucket outside of the plugin.

# Autogenerated Input/Output Documentation by Arcaflow-Docsgen Below

<!-- Autogenerated documentation by arcaflow-docsgen -->
## MinIO (`minio`)

Runs the MinIO server and sets up a bucket

### Input

<table><tbody>
<tr><th>Type:</th><td><code>scope</code></td><tr><th>Root object:</th><td>InputParams</td></tr>
<tr><th>Properties</th><td><details><summary>minio_password (<code>string</code>)</summary>
                <table><tbody><tr><th>Name:</th><td>MinIO password</td></tr><tr><th>Description:</th><td>The MinIO server password</td></tr><tr><th>Required:</th><td>No</td></tr><tr><th>Type:</th><td><code>string</code></td></tbody></table>
            </details><details><summary>minio_user (<code>string</code>)</summary>
                <table><tbody><tr><th>Name:</th><td>MinIO username</td></tr><tr><th>Description:</th><td>The MinIO server username</td></tr><tr><th>Required:</th><td>No</td></tr><tr><th>Type:</th><td><code>string</code></td></tbody></table>
            </details><details><summary>run_duration (<code>int</code>)</summary>
                <table><tbody><tr><th>Name:</th><td>run duration</td></tr><tr><th>Description:</th><td>Time in seconds that the PCP plugin runs before being forceably stopped</td></tr><tr><th>Required:</th><td>Yes</td></tr><tr><th>Type:</th><td><code>int</code></td>
</tbody></table>
            </details></td></tr>
<tr><td colspan="2"><details><summary><strong>Objects</strong></summary><details><summary>InputParams (<code>object</code>)</summary>
            <table><tbody><tr><th>Type:</th><td><code>object</code></td><tr><th>Properties</th><td><details><summary>minio_password (<code>string</code>)</summary>
        <table><tbody><tr><th>Name:</th><td>MinIO password</td></tr><tr><th>Description:</th><td>The MinIO server password</td></tr><tr><th>Required:</th><td>No</td></tr><tr><th>Type:</th><td><code>string</code></td></tbody></table>
        </details><details><summary>minio_user (<code>string</code>)</summary>
        <table><tbody><tr><th>Name:</th><td>MinIO username</td></tr><tr><th>Description:</th><td>The MinIO server username</td></tr><tr><th>Required:</th><td>No</td></tr><tr><th>Type:</th><td><code>string</code></td></tbody></table>
        </details><details><summary>run_duration (<code>int</code>)</summary>
        <table><tbody><tr><th>Name:</th><td>run duration</td></tr><tr><th>Description:</th><td>Time in seconds that the PCP plugin runs before being forceably stopped</td></tr><tr><th>Required:</th><td>Yes</td></tr><tr><th>Type:</th><td><code>int</code></td>
</tbody></table>
        </details></td></tr>
</tbody></table>
        </details></details></td></tr>
</tbody></table>

### Outputs


#### error

<table><tbody>
<tr><th>Type:</th><td><code>scope</code></td><tr><th>Root object:</th><td>ErrorOutput</td></tr>
<tr><th>Properties</th><td><details><summary>error (<code>string</code>)</summary>
                <table><tbody><tr><th>Required:</th><td>Yes</td></tr><tr><th>Type:</th><td><code>string</code></td></tbody></table>
            </details></td></tr>
<tr><td colspan="2"><details><summary><strong>Objects</strong></summary><details><summary>ErrorOutput (<code>object</code>)</summary>
            <table><tbody><tr><th>Type:</th><td><code>object</code></td><tr><th>Properties</th><td><details><summary>error (<code>string</code>)</summary>
        <table><tbody><tr><th>Required:</th><td>Yes</td></tr><tr><th>Type:</th><td><code>string</code></td></tbody></table>
        </details></td></tr>
</tbody></table>
        </details></details></td></tr>
</tbody></table>

#### success

<table><tbody>
<tr><th>Type:</th><td><code>scope</code></td><tr><th>Root object:</th><td>SuccessOutput</td></tr>
<tr><th>Properties</th><td><details><summary>access_key (<code>string</code>)</summary>
                <table><tbody><tr><th>Name:</th><td>access key</td></tr><tr><th>Description:</th><td>The MinIO server access key (user)</td></tr><tr><th>Required:</th><td>Yes</td></tr><tr><th>Type:</th><td><code>string</code></td></tbody></table>
            </details><details><summary>secret_key (<code>string</code>)</summary>
                <table><tbody><tr><th>Name:</th><td>secret key</td></tr><tr><th>Description:</th><td>The MinIO server access secret (password)</td></tr><tr><th>Required:</th><td>Yes</td></tr><tr><th>Type:</th><td><code>string</code></td></tbody></table>
            </details></td></tr>
<tr><td colspan="2"><details><summary><strong>Objects</strong></summary><details><summary>SuccessOutput (<code>object</code>)</summary>
            <table><tbody><tr><th>Type:</th><td><code>object</code></td><tr><th>Properties</th><td><details><summary>access_key (<code>string</code>)</summary>
        <table><tbody><tr><th>Name:</th><td>access key</td></tr><tr><th>Description:</th><td>The MinIO server access key (user)</td></tr><tr><th>Required:</th><td>Yes</td></tr><tr><th>Type:</th><td><code>string</code></td></tbody></table>
        </details><details><summary>secret_key (<code>string</code>)</summary>
        <table><tbody><tr><th>Name:</th><td>secret key</td></tr><tr><th>Description:</th><td>The MinIO server access secret (password)</td></tr><tr><th>Required:</th><td>Yes</td></tr><tr><th>Type:</th><td><code>string</code></td></tbody></table>
        </details></td></tr>
</tbody></table>
        </details></details></td></tr>
</tbody></table>
<!-- End of autogenerated documentation -->
