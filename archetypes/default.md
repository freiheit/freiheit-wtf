+++
date = '{{ .Date }}'
draft = true
title = '{{ replace .File.ContentBaseName "-" " " | title }}'
description = '{{ replace .File.ContentBaseName "-" " " | title }}'
keywords = ['{{ replace .File.ContentBaseName "-" " " | title }}']
tags = ['FIXME']
+++
