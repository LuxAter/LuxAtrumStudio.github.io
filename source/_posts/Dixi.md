title: Dixi
author: Arden Rasmussen
tags:
  - Javascript
  - Python
categories:
  - CS
  - Web
date: 2018-05-15 10:37:00
---
Dixi is an open source, lightweight instant messaging server and client system.

[![GitHub Link](https://img.shields.io/badge/Github-Dixi-blue.svg?style=for-the-badge)](https://github.com/LuxAtrumStudio/dixi) ![](https://img.shields.io/github/repo-size/LuxAtrumStudio/dixi.svg?style=for-the-badge)

<!-- more -->

## BackEnd ##

The backend of **Dixi** is powered by an express server, with a mongodb for user, and channel data. By default any channel that have been inactive for more than 30 days will have a messages announcing the deletion, and then will be deleted after 24 hours. Only messages from the past two weeks are sent to the client in order to improve speed, but more messages can be requested.

## FrontEnd ##

The frontend of **Dixi** has been primarily constructed for terminal usage, but a web client is currently in progress. All messages are rendered using markdown rendering, allowing for significantly improved usability of the messaging system.

### CLI ###

The *command line interface* is the most direct way to interface with **Dixi**.  It allows for creating of channels, and users. It also implements a terminal based markdown renderer, including proper code highlighting. This interface also provides admin tools, such as system posts, and posts to all channels.  These tools are only available through this interface. The **cli** also provides a listener method, which creates a class that listens for any new posts to active channels, and will alert the user of there is a new post.

### TUI ###

The *terminal user interface* is a semi-graphical interface, using unicode characters to create a display completely within the terminal. This interface has all of the tools of the **cli** with the exception of the admin tools. This interface automatically watches for new posts, and updates the displayed channels accordingly.
