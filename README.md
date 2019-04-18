# Mozaïk jenkins widgets

[![License][license-image]][license-url]
[![Travis CI][travis-image]][travis-url]
[![NPM version][npm-image]][npm-url]
[![Dependencies][gemnasium-image]][gemnasium-url]
[![Coverage Status][coverage-image]][coverage-url]
![widget count][widget-count-image]

## Jenkins Client Configuration

In order to use the Mozaïk jenkins widgets, you must configure its **client**.

### parameters

key                 | env key                         | required | description             | notes
--------------------|---------------------------------|----------|-------------------------|-----------------------------------------------
`baseUrl`           | JENKINS_API_BASE_URL            | yes      | *jenkins base url*      |
`basicAuthUser`     | JENKINS_API_BASIC_AUTH_USER     | yes      | *jenkins auth user*     |
`basicAuthPassword` | JENKINS_API_BASIC_AUTH_PASSWORD | yes      | *jenkins auth password* |
`customCa`          | JENKINS_API_CUSTOM_CA           | no       | *jenkins certificate*   | require `mozaik-ext-jenkins >= 1.1.0`

### usage

```javascript
{
  //…
  api: {
    jenkins: {
      baseUrl: 'https://my-jenkins.ci',
        basicAuthUser:     'user',
        basicAuthPassword: 'password'
    }
  }
}
```



## Jenkins Job Builds

![jenkins job builds](https://raw.githubusercontent.com/plouc/mozaik-ext-jenkins/master/preview/jenkins.job_builds.png)

> Show jenkins job builds.

### parameters

key     | required | description
--------|----------|---------------
`job`   | yes      | *jenkins job identifier*
`title` | no       | *Widget title (`Jenkins job builds` if none provided)*

### usage

```javascript
{
  type: 'jenkins.job_builds', job: 'my-job',
  columns: 1, rows: 1, x: 0, y: 0
}
```



## Jenkins Job Builds Histogram

![jenkins job builds histogram](https://raw.githubusercontent.com/plouc/mozaik-ext-jenkins/master/preview/jenkins.job_builds_histogram.png)

> Show jenkins job builds histogram.

### parameters

key   | required | description
------|----------|---------------
`job` | yes      | *jenkins job identifier*
`cap` | no       | *number of builds to show*

### usage

```javascript
{
  type: 'jenkins.job_builds_histogram', job: 'my-job',
  columns: 1, rows: 1, x: 0, y: 0
}
```



## Jenkins Job Status

![jenkins job status](https://raw.githubusercontent.com/plouc/mozaik-ext-jenkins/master/preview/jenkins.job_status.png)

![jenkins job status bold](https://raw.githubusercontent.com/plouc/mozaik-ext-jenkins/master/preview/jenkins.job_status_bold.png)

> Display job current build status.

### parameters

key      | required |description                                   | notes
---------|----------|----------------------------------------------|-----------------------------------------
`job`    | yes      | *jenkins job identifier*                     |
`layout` | no       | *widget layout* (none for default or 'bold') | require `mozaik-ext-jenkins >= 1.1.0`

### usage

```javascript
{
  type: 'jenkins.job_status', job: 'my-job',
  columns: 1, rows: 1, x: 0, y: 0
}
```


## Jenkins Job Status With Progress

![jenkins job status](./preview/jenkins.job_status_progress.png)

> Display job current build status with progress % - based on Job Status - bold.

### parameters

key      | required |description                                   | notes
---------|----------|----------------------------------------------|-----------------------------------------
`job`    | yes      | *jenkins job identifier*                     |

### usage

```javascript
{
  type: 'jenkins.job_status_progress', job: 'my-job',
  columns: 1, rows: 1, x: 0, y: 0
}
```


## Jenkins View

![jenkins view](https://raw.githubusercontent.com/plouc/mozaik-ext-jenkins/master/preview/jenkins.view.png)

> List view jobs

### parameters

key     | required | description
--------|----------|---------------
`view`  | yes      | *jenkins view identifier*
`title` | no       | *widget title (view name used if none provided)*

### usage

```javascript
{
    type: 'jenkins.view', view: 'dev-env',
    columns: 2, rows: 1, x: 0, y: 0
}
```


## Jenkins Job Test Result

![jenkins job test result](./preview/jenkins.job_test_result.png)

### parameters

key    | required | description
-------|----------|--------------
`job`  | yes      | *jenkins job identifier*

### usage

```javascript
{
   type: 'jenkins.job_test_result',
   job: process.env.JENKINS_JOB_0,
   columns: 1, rows: 1,
   x: 0, y: 1
}
```



[license-image]: https://img.shields.io/github/license/plouc/mozaik-ext-jenkins.svg?style=flat-square
[license-url]: https://github.com/plouc/mozaik-ext-jenkins/blob/master/LICENSE.md
[travis-image]: https://img.shields.io/travis/plouc/mozaik-ext-jenkins.svg?style=flat-square
[travis-url]: https://travis-ci.org/plouc/mozaik-ext-jenkins
[npm-image]: https://img.shields.io/npm/v/mozaik-ext-jenkins.svg?style=flat-square
[npm-url]: https://www.npmjs.com/package/mozaik-ext-jenkins
[gemnasium-image]: https://img.shields.io/gemnasium/plouc/mozaik-ext-jenkins.svg?style=flat-square
[gemnasium-url]: https://gemnasium.com/plouc/mozaik-ext-jenkins
[coverage-image]: https://img.shields.io/coveralls/plouc/mozaik-ext-jenkins.svg?style=flat-square
[coverage-url]: https://coveralls.io/github/plouc/mozaik-ext-jenkins
[widget-count-image]: https://img.shields.io/badge/widgets-x4-green.svg?style=flat-square
