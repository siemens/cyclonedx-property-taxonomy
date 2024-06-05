# Siemens CycloneDX Property Taxonomy, v1.3.0

This is the official Siemens property taxonomy for CycloneDX.

For more information about CycloneDX property taxonomies, refer to
their [official documentation](https://github.com/CycloneDX/cyclonedx-property-taxonomy).

<table>
<thead>
    <tr>
        <th>Property</th>
        <th>Description</th>
        <th>Scope</th>
    </tr>
</thead>
<tbody>
    <tr style="vertical-align: top;">
        <td><b>siemens:direct</b></td>
        <td>A flag indicating whether the component is a direct dependency (<code>true</code>) or a transitive
            dependency (<code>false</code>).</td>
        <td><code>components[]</code></td>
    </tr>
    <tr style="vertical-align: top;">
        <td><b>siemens:filename</b></td>
        <td>The simple file name of the component, without path. For example, the simple name of a JAR file.</td>
        <td><code>components[]</code></td>
    </tr>
    <tr style="vertical-align: top;">
        <td><b>siemens:internal</b></td>
        <td>A flag indicating whether the component is an internal ("in-house") component (<code>true</code>) or not
            (<code>false</code>).</td>
        <td><code>components[]</code> or <code>metadata/component</code></td>
    </tr>
    <tr style="vertical-align: top;">
        <td><b>siemens:legalRemark</b></td>
        <td>Pass-through free text for legal remarks that need to be included in attribution information. A "legal
            remark" is provided by the people creating the SBOM, normally the team behind the product described by
            the SBOM.</td>
        <td><code>components[]</code></td>
    </tr>
    <tr style="vertical-align: top;">
        <td><b>siemens:primaryLanguage</b></td>
        <td>Indicates the primary programming language the artifact is written in.</td>
        <td><code>components[]</code></td>
    </tr>
    <tr style="vertical-align: top;">
        <td><b>siemens:profile</b></td>
        <td>A Siemens-internal declaration which indicates the use case for this SBOM. Depending on the profile,
            Siemens-internal validation tooling will expect different fields to be present or not present in the
            SBOM.</td>
        <td><code>metadata</code></td>
    </tr>
    <tr style="vertical-align: top;">
        <td><b>siemens:sbomNature</b></td>
        <td>Used to indicate the nature of the entire SBOM document. Possible values are:
            <ul><li><code>binary</code> – The SBOM contains binary components.</li>
                <li><code>source</code> – The SBOM contains source components.</li>
            </ul>
            A binary component may have source information attached, and vice versa.</td>
        <td><code>metadata</code></td>
    </tr>
    <tr style="vertical-align: top;">
        <td><b>siemens:thirdPartyNotices</b></td>
        <td>The contents of all third-party notices found for the component, if any. Note that this is <i>not</i> the
            path to the notice files, but the actual notice text (which may be quite a lot of text). Third-party
            notices are provided by the component's author.<br>
            Since CycloneDX allows only a single String value for this, we separate different notice files by two
            consecutive line feeds.</td>
        <td><code>components[]</code></td>
    </tr>
    <tr style="vertical-align: top;">
        <td><b>siemens:vcsClean</b></td>
        <td>A flag (<code>true</code> or <code>false</code>) indicating whether the Git workspace was clean when the
            SBOM was created, i.e. all changes had been committed.</td>
        <td><code>metadata</code> or <code>metadata/component</code></td>
    </tr>
    <tr style="vertical-align: top;">
        <td><b>siemens:vcsRevision</b></td>
        <td>The most recent VCS hash, for example a Git commit hash. Together with <code>siemens:vcsClean</code>, this
            additional value allows ensuring accurate reproducibility of the SBOM.</td>
        <td><code>metadata</code> or <code>metadata/component</code></td>
    </tr>
</tbody>
</table>

The **Scope** column describes which `properties` section is the intended location for the property. For example,
a scope of `metadata` means that the property is intended for use in `metadata/properties`. This is meant as a
recommendation only.


## Contributing

These properties are maintained by Siemens. Feel free to raise an issue if you have any questions.


## License

Copyright 2022 Siemens AG.

Licensed under [Apache License 2.0](./LICENSE).
