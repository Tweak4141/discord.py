Discord.py
==========

.. image:: https://discord.com/api/guilds/740523643980873789/embed.png
   :target: https://discord.gg/Q5mFhUM
   :alt: Discord server invite
   
.. image:: https://img.shields.io/pypi/v/discord.py.svg
   :target: https://pypi.python.org/pypi/discord.py
   :alt: PyPI version info
.. image:: https://img.shields.io/pypi/pyversions/discord.py.svg
   :target: https://pypi.python.org/pypi/discord.py
   :alt: PyPI supported Python versions

A modern, easy to use, feature-rich, and async ready API wrapper for Discord written in Python.

About this fork
---------------
As we know, the discord.py wrapper has been discontinued by ``Rapptz`` for a number of reasons, which you can find `here <https://gist.github.com/Rapptz/4a2f62751b9600a31a0d3c78100287f1>`__.

But we at Mecha Karen love this amazing wrapper, so we decided to continue it. Keeping it both up to date with other libraries and the discord API providing rich features for all!

Key Features
-------------

- Modern Pythonic API using ``async`` and ``await``.
- Proper rate limit handling.
- Optimised in both speed and memory.

Installing
----------

**Python 3.8 or higher is required**

This fork will not be uploaded to PyPi for the time being.

.. code:: sh

    # Linux/macOS
    python3 -m pip install -U git+https://github.com/Mecha-Karen/discord.py/

    # Windows
    py -3 -m pip install -U git+https://github.com/Mecha-Karen/discord.py/

Otherwise to get voice support you should run the following command:

.. code:: sh

    # Linux/macOS
    python3 -m pip install -U git+https://github.com/Mecha-Karen/discord.py#egg=voice

    # Windows
    py -3 -m pip install -U git+https://github.com/Mecha-Karen/discord.py#egg=voice


To install the development version, do the following:<br/>
This section will become useful once we push this fork to PyPi

.. code:: sh

    $ git clone https://github.com/Mecha-Karen/discord.py
    $ cd discord.py
    $ python3 -m pip install -U .[voice]


Optional Packages
~~~~~~~~~~~~~~~~~~

* `PyNaCl <https://pypi.org/project/PyNaCl/>`__ (for voice support)

Please note that on Linux installing voice you must install the following packages via your favourite package manager (e.g. ``apt``, ``dnf``, etc) before running the above commands:

* libffi-dev (or ``libffi-devel`` on some systems)
* python-dev (e.g. ``python3.6-dev`` for Python 3.6)

Quick Example
--------------

.. code:: py

    import discord

    class MyClient(discord.Client):
        async def on_ready(self):
            print('Logged on as', self.user)

        async def on_message(self, message):
            # don't respond to ourselves
            if message.author == self.user:
                return

            if message.content == 'ping':
                await message.channel.send('pong')

    client = MyClient()
    client.run('token')

Bot Example
~~~~~~~~~~~~~

.. code:: py

    import discord
    from discord.ext import commands

    bot = commands.Bot(command_prefix='>')

    @bot.command()
    async def ping(ctx):
        await ctx.send('pong')

    bot.run('token')

You can find more examples in the examples directory.

Links
------

- `Documentation <https://discordpy.readthedocs.io/en/latest/index.html>`_
- `Official Discord Server <https://discord.gg/r3sSKJJ>`_
- `Discord API <https://discord.gg/discord-api>`_
