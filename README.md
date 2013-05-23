# Developer Web Server
grunt-devserver provides a simple way to quickly get a development server serving up your content with

* no caching content
* CORS headers for cross-domain requests
* logs requests to console
* install globally and run from command line or Grunt 0.4.x
* quickly configure https server

As a developer I needed a lightweight way to serve up client-side applications and content in isolation from a larger
server application.  Something that supported a rapid workflow and integrated with my tools.

## Installation
Install it from the command line into your project
```
npm install grunt-devserver --save-dev
```
Or add it to your package.json devDependicies
```
"devDependencies": {
    "grunt-devserver": "*"
}
```
Or install it globally
```
npm install grunt-devserver -g
```

## Usage
### From the Command Line
Once grunt-devserver has been installed globally you can run it from any folder by typing ```devserver```

Command line options:
```
-t, --type (server type) http|https (default is http)
-p, --port (port number) listen on this port
-f, --folder (full path to a folder) serves this folder
--cache (method) the method to return in the Cache-Control HTTP header. Default is no-cache.
```

### <img alt="" src="data:image/png;base64,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" /> From Grunt 0.4.x
In your GruntFile.js file add this to your grunt configuration:
```
devserver : { options: { 'type' : <string> (http|https defaults to http)
                       , 'port' : <port number> (defaults to 8888)
                       , 'base' : <directory> (defaults to .)
                       , 'cache' : <string> (defaults to 'no-cache')
                       }
            }
```

Load the devserver task:
```
grunt.loadNpmTasks(grunt-devserver)
```

and execute using:
```
grunt devserver
```

### <img alt="" src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAEoAAABACAYAAAC9S+EXAAAEJGlDQ1BJQ0MgUHJvZmlsZQAAOBGFVd9v21QUPolvUqQWPyBYR4eKxa9VU1u5GxqtxgZJk6XtShal6dgqJOQ6N4mpGwfb6baqT3uBNwb8AUDZAw9IPCENBmJ72fbAtElThyqqSUh76MQPISbtBVXhu3ZiJ1PEXPX6yznfOec7517bRD1fabWaGVWIlquunc8klZOnFpSeTYrSs9RLA9Sr6U4tkcvNEi7BFffO6+EdigjL7ZHu/k72I796i9zRiSJPwG4VHX0Z+AxRzNRrtksUvwf7+Gm3BtzzHPDTNgQCqwKXfZwSeNHHJz1OIT8JjtAq6xWtCLwGPLzYZi+3YV8DGMiT4VVuG7oiZpGzrZJhcs/hL49xtzH/Dy6bdfTsXYNY+5yluWO4D4neK/ZUvok/17X0HPBLsF+vuUlhfwX4j/rSfAJ4H1H0qZJ9dN7nR19frRTeBt4Fe9FwpwtN+2p1MXscGLHR9SXrmMgjONd1ZxKzpBeA71b4tNhj6JGoyFNp4GHgwUp9qplfmnFW5oTdy7NamcwCI49kv6fN5IAHgD+0rbyoBc3SOjczohbyS1drbq6pQdqumllRC/0ymTtej8gpbbuVwpQfyw66dqEZyxZKxtHpJn+tZnpnEdrYBbueF9qQn93S7HQGGHnYP7w6L+YGHNtd1FJitqPAR+hERCNOFi1i1alKO6RQnjKUxL1GNjwlMsiEhcPLYTEiT9ISbN15OY/jx4SMshe9LaJRpTvHr3C/ybFYP1PZAfwfYrPsMBtnE6SwN9ib7AhLwTrBDgUKcm06FSrTfSj187xPdVQWOk5Q8vxAfSiIUc7Z7xr6zY/+hpqwSyv0I0/QMTRb7RMgBxNodTfSPqdraz/sDjzKBrv4zu2+a2t0/HHzjd2Lbcc2sG7GtsL42K+xLfxtUgI7YHqKlqHK8HbCCXgjHT1cAdMlDetv4FnQ2lLasaOl6vmB0CMmwT/IPszSueHQqv6i/qluqF+oF9TfO2qEGTumJH0qfSv9KH0nfS/9TIp0Wboi/SRdlb6RLgU5u++9nyXYe69fYRPdil1o1WufNSdTTsp75BfllPy8/LI8G7AUuV8ek6fkvfDsCfbNDP0dvRh0CrNqTbV7LfEEGDQPJQadBtfGVMWEq3QWWdufk6ZSNsjG2PQjp3ZcnOWWing6noonSInvi0/Ex+IzAreevPhe+CawpgP1/pMTMDo64G0sTCXIM+KdOnFWRfQKdJvQzV1+Bt8OokmrdtY2yhVX2a+qrykJfMq4Ml3VR4cVzTQVz+UoNne4vcKLoyS+gyKO6EHe+75Fdt0Mbe5bRIf/wjvrVmhbqBN97RD1vxrahvBOfOYzoosH9bq94uejSOQGkVM6sN/7HelL4t10t9F4gPdVzydEOx83Gv+uNxo7XyL/FtFl8z9ZAHF4bBsrEwAAAAlwSFlzAAALEwAACxMBAJqcGAAAG41JREFUeAHtW3l81dWVP7/lvd9b87KQhAQIYVcKVjAWEYthcXeqtOpo1am0Fqq22qlgwSqQVkvVVqettmCn1LZKLdipOsyHtpZNioAQkVVkUUIghOzJ23/rfM/N+6UPBlqy0P4z95Obe++5527fe8652+9JjuPQP8NJcGhXhbfRB+tc+pBVxkIZ+1zK9BWP9M8ACgNWssFB2uPz+QYhLLUsqwCDC8qyrNm2nQStHbzHdV0/grDDHTjoKtKmmz7f4T8cKAywC6RAIHA5wLgVA54E+hAMNh9ePsOg46DVgm8L+H6XSqVWMQ/XhYAl8ryrxfkDauVtCg3Nk6sxklWrSq2FCxfaLkjhcLgIEvIDpO/iAffAbYDEzUskEgwcqzCdd7B4MvrWk+SsW8RqcUq9iyorBS0YDBZrmrYDquYgZG/CGxlvIWRvZ3lOuzwcdpVDHV9w2wFWYtLddF+HfStRVVUyQXKEhOyrCrW36hPZXLcWj9hYXn5PiuleTXtJkWUeoI4kqw777jhWMwPey4VQz+3pdPq3ECwZ8fNm4M9kD7j97rsskFo3zb+zvTVVLSnSH4Ne9U/e7Wse4gpnzpzi0xRpLAbESVaZM4LEo2UrfZZRczkGKQnPdurfOGSQXDXkdF+7XgIF+8C2CN11Jal986PzcoLay6GQfyTTVbOZzKajF3LHf/GLdSmPIh3KWF5hW04fEOcF4HMdifwIzwIWF/PwP7j9/O98gsT19xioKpYgzCPdusKilStEPW2bH5sR0DyLk7pN0WicjKP76MjGta/HP3x7PjfGLpqyd3shTBilDO/waNnzhoo9g9MuOdQsW9RBDgUzdJcvK5SZHwDtQ8COVS8zB52EvvzPbfXESbyKccGjy+/MK/v8K60nqqsCQbKfUFSNrETMjn+0J23GWpbkT/rcn+VgOBesJ5hf05SPYqYoyuB2DYwTLGKWZNNQS6X+hkK1XpNqAZjHkYVRQrbruAIxOQg/donnM3Qb604bPB4xwI5Njz7vkfVd2z4l9Q8pytXhgDY6lkg5ydrDpHi0zfkTrq1QJOl/7Gjbnrq1c+7A7N8Z9qlPCYUCICTZEjyHZEOKLMmim1J+uscI0w2QpZl6mKamfGSA7vJlQjsTnixP+d7LdL6nk35OY+9+5eurFKpcaEa3Vl0RDmsPKAEPhSdQoWNYV0s5XjLqTjiS6tH9ZcMvC3qkQEI3KRTQ5MaWxPLSkSXb+x848ewSKnvQS3Z5msTRRWHUVchTDUx4I1kUgbAwLQBbP5F8dFsqSAPAYYDKswRoFR9iR8ksXqC2zANpHrQujYnwIOQVsc9d94EK1wkj7Fj6QMPWKGFKFLhwwg0gXmwn02Slk45WVOpTvV6KNTaY6ZYG0x40Ui0tiqibnvvM4+XXL/nDQWnkHQEAFWMbJyBhOyWJWC2AYr1qAmiFAIdFfjByR8EDWJHmQmGSpTyS322U9eskr2fSdCN8I0BqP19gdV/1oqU82WQaek1KNx0tkk+S6ptvp5PjYok0yV5NkX0wwamYvfe93eqJI4d9cnONap44SCUdh8V2wCT7Az4FAxKJtwEsKSa8BrCCQmb4LNMpQSxpfng9w8PiAn5htQeSZ4WTdj5ZYMtN76ixTQCpH0sUgwW2PnXdBqpqQ+eKnV/5/S1kWptyBpSQJ6cgoLec9DmSTHIgTKqdtmt275ZnP7OhvqaVVpmNH1PtwYP1b64/1sK9b/YZdVFUA4mSEziqxQFCO9KscpASoX4ppJvhi5EOACjOT4AvDn6EShNg3keGuHWYaeXdlZadWlVV3wZIwQxY3deWvwFtz3bmvHfCtqBp/TcrPJrnT5GQJ6+p5igpwbBjGTop8Rbpww9raOL8LXeg06/S8lFDr3+2Y+7q6vp/hXmJl5InCHXKY9GEGRfdkzWF/NDf9pRFxwBIEQCqBxjDEPr8KqVNh+xOXGC5Om3Yfko1psOKGpIlb2O7eZ/HQ6x+RYZhTOFKAVqf7dZ7BpQYGu+jFtrxjd+6yPLKz0Abpjt6SrbSuq0EArLHTJFSu/1q7a6/vEXVj8558/drZ9305NYR2CDgD+CkMza3ANtLnvuTCVEr5UBrOjJ5rEA+NBPtBJNKoNJJCFGbOA1hfw4G3RB4XzAwOO6D2thur9d7FGAtA1iLAFSfXcX0AigMIiNZPMK2dx6dqSjKMkwjWxAroKlKe1PzZtkfaMkrzruhdc8u2r9rj+5InkRKd0LH6mIqBIf0VJIamxKwUV5sKbzkUW0qyoe1kmXC3RQ1NBtQNomMtE6aolNhvxApXg2mnJwh5TmSrShbf7O16eGfvnFoE/cD5unTqkqvA6SpuKHYibBPVsLeAcU921flpdELdVpZ5W0fkN4b9HmGx5O6BbMi+3yapPk81N6RIv34QbKbjlKsIUrBgQPIM2gUGdg6NNY1kieUQwWFETp59CR9tPcQVVw5nvxBH3W0Rum9je/TmAljKadfLjU3tJGTilPhgGJSZNvRa/dDkbGPl5UXi7+6ZTZAEXddiqr+TJakQZCqazvBk3icYhHidE9c7w3e6EXQk4VUPbTOGWkVNmFbMFwysD+CfUjGk7GOYzWmZCRy4yeOpZN17Z6Wmo9lP8z2iNFY4KFRg/JySYV4xDrilEynKa+0iEJFBbBLGtmQnDAAisWTFCnKpbIRA8iAnZIUWCnLkA4eaLH8HUcVLZL3pZNzh/8YWOxhEGzLekLxeDZ6PJ4rAdYGkHicGX1mju67bq96pzexcuWtoo78X7+TH92/b1C8+ThZyQ4lh2JS6tjBj1s3v3R1quFgZby26RtqOi57NNXWY0nHhtGHegqfwrZCT5s0aHgZBQIaxZpbKYWzYqyplfIBVOmQUkomdKipTkG/h/xehbcnZCZTZPJxyLEdxXD4mEirHxyhAbAaRN+ChM3K9NdEHEtFz12vJWrobR/xEmTFfxirtEe/PyDx6RB5P5Frxr12nZ1KPj1ysbNNdO+5y99N66lvlBVHhumRTin68HAj7dhZQ0ePt8G227A7DiUbGigXNjoC1WuJJrCF8JKv4Djf95IfwA4ZlE/jx5VTWT+PM3BkgRJMadRuStsvuCyyg9tZfYjoOoQA6xVg8xP4YsRPIuQ9nNhOMF93Xe9tFFQMvbLfl4YsyyVlZhJ9cSYoc0dvGf8c0QprfdUUtXwwqeX3rEsd/tm0y8Oq+WwsLV+0eq/j/83L1XSsLSYupXhdY9HkKxaePVdXeEPK6yEbGM7nkQ4fUuzc+dkLpemjKOZV7XdjtvzQsC+t20O40ZAWLeIxWQDGi33VVsQXm6a5AulerYC9AyoDUpU0xPcZos25JF+MTSRWMGn6OOfwmuqKCs8l27cL2zC7QvIs3e4Yz94xfFD1B60bq3e2DI5g3KHSHIVXSgwES5ZC6YZm6nfRRTTx2hto3cpXKHHiKDa0eHPA5SUGzaJC7XUdVhobsoqKwvemXlgy+e5f7Yy/OLvCM2vpdt6Vs4rxuGxsFV5G2AQ79XWQe7Wn6qXqVfIk27eRPAgbxzKedeyS+Bwm6r0kHBYrTRU6uRRHi2oMZvmrh5dgJIMHlORYUCfFhG3iG1wYYNKw+sWBgN9QyRuMUGs75KcdiAQd0mNx1ApMsW3IKQkrmA971/bG8Xu2N//47l/RF12QAIwDULh9fp15H+FUeAZZ3IByPqe763igPXbVFBUGMkZmGcaXx0eMWjKlP1LCx5VWrV/PkiItyrTw76/tnZdfHLw+XBxwjJSumDDODBBLVCASovbjzRTIC9Jd0Q4aM28efTE3SGkMOdnYSv4IX+Fh9KZFRhKGXDek3P5BrIa+mZML/PdyXiUw5RBO9AuYwGJRP3QB8yecoGfi3Qp6pXoV2Mxth6RMlyJ3Rkh6mVs+pJq0S9G/4qT0peigcitoK2AzKgsCE2GH/oIkq0ASRx9N8apiovC2RyeOtYuL8Ce+fytNGtyPzJYUyf389Ifdx2jBojcphIKFg3I7VRRCgT2YbelGCs9WASTbHNmesLExdeA2tLmysw0D24NJKPY8bNRVaLMJ/emx+mG+eu74zY7dmkAsjLnmqIG5xJpFozkBZzdmZhnWdRz0BYqDUaiKv60+Sm3QCBhrvrqjKz5VTvd9uZIqPjmQTh6vpw4tRnm4qplx3VgqgJQtWbqOtu2rF2Ci0w6slhwuCgZsy4ZNpFzJli9CNQfQHkuNUC8AkwBALGX8GMGuxxLVK6AqMx0qMzRfCH3ob8g0ARdtIwgzKY3xopM6REAgWNKcWHoiz7/LUeSbU23xsRdOHDquuH+kMDfidz5xYal06cVlVFgQIlzdUF5hIeUWFIiNJW+TpkwaQaOGFdHW92rog4P1FO1ISXV1rcePbKt531cY2km6/buN7QmxPViHZ3YAxJPFjkFi0EQfmNBT1yvVexEdmgXVWy6VzvKQvDQFk5nEHdNeCNZf1PS0aiO61lXP0ztY/+e5zxQWBOckUobpxUJuQf3S4uSDW0xeBSF7DmgAG0Ul3LXjEg/nuzSA9KiK1NqemFs6/Qffz64X5Xg8bMzF+Q6qNw35z0D1poDMl3o9Vr1eGvPObm6g1PHV2O38mRLSdgz3Amjfw2bOI5zLNmwKViF0UqrAFoHWVwkpzo34WhScAwGDlEwZKGXi/CaRirsS2B0BkIyjCqcl0FO4bUhihcRYJZ/mocL8nCau/9DqBzVULepnkJgGJ1QM9FLE4wySoGY0IBPvVtAroO7INDyS/IevIn/HLTC508mvJDHMX1L0Gimg8X02rev86kStriaz+kDnVTKuEJI2wMEajvFARwCKaZgUb+vAscSE9EhY2XSR5pURr8tiYGz40wCsvQPnFzg9VsD4mPxPMHT+E3GQRqPyuix6j6O9slEboPuVaPphGnnodtpx4ARZFW/78FIu6/jwQJVCtrIY3wrYePJ+Gp0WG8/qF2d3dtajxjiSbV1lSE7biZPUCmPOcwDpoYLBA6mwfKAoA+wcGbhCIfG6oPIXLjQah3GRmfkHYFj93APwxYhv5CyQu76iyeY/13ivgFqITRwvx1j+zd+GpLVkqxVky1Ri+mT01OYLEEjGU/iY4tPo6NP4XOcddxD5qrcOKyEMNgZmQq4sW2JV6z9iCIUL+5GOhwofznuBSBjyCdiwurGRUnDbaaUtO8+0G3iQ61fpSuUlp9wMsAFng14CGzUE7T2ZASN7TjKkcw8Y/XPnPgMnOiTOUOOlwMTjXmdTWnIkiArXyksPrzZCZ7iXuFR/NyegbjnaFtv2fGH56FvmT54fmFSGJxh0w8DLHpY4QEeygiKsj6iFVQ1ChGdlpsG+Nyakxjf30/afbL3pdqfxTe5SFfqAScMuQUiOMOQ4vnwZY5sFNb4MIZ/9emzIRb19ABSDLdCWfL4N2LBMxhBZ9MUSzcKAIdqYZiWO24F8S6KWoES3tTk0H28tkXvGUmDqUNIG5pAcxGO7gtL4Y3QhYzgN4ngDY280xCm+s55Sy/c7HYdqpe+Q0f7fuekfLm0zn+CVF7d2nhfBja6IrQCkaQOqWItzHnDs3YGYgeqV6nEFDBI6IvQfG6cliE/O1Mvg8VDZAyTbwauv1aLaTksyLkuBfEVOaNTx0naKvrSftCvxmjMSj1Q4lkhhjdIo5GnD20urSWZtgtJvngD6jdg5BhhufKPYEKGYuWAFhaZXSMO/gLPkIV2S+OiU8qnqDdheDAFIS5HuE9dr1eNeABwh1gwYjPd6kK6Axw0TecK4725RDLopGaQLMMyntCjExaKpSZ/zNI5hEcxVTLza8SJmIKXiex6DdmO/fdknryRn5zHk7oSElYm8IGI1oMyWGq0DctIps7zqVyhyHMflmY84J99CJdB5zw5I9qq0YTyOPvXqeoXrY4d5671jcc90CO8B1gKkuVIPTqJWC9aokK3SZDxjYo+FFk0qxkcYa/1p6VWKUitACUFLg5SDm4c8gMGfceLNL7+YIt99kLT7p2KvTxTKgWqCvgMwPolSB3z4igOX40e9urGD0gPQ4p8kTboTIC3CKUHTTfPb3Ak4oYqd0Z7/7xOJ4uYBFCxL5z0Qzrvf1RVpfn9HsurVlHx/Ih87P5Ue8zdSru2FPHR+KKZjbZwGSZuB6zqWtjycOFhi8DCPx02bxlwyEmrXRNGGk5AihTZhU7vEl6BPpVSKqg4NMBV8ImPSXjVpPWsWKftQ839qbenxaX9ltSO+7xSGnfvXW9drG+V2IGOrhISmjfSjIY82tl6hG8n2GKPJq66jpDDR2AeRDivD9x4Ry0tr/Elag/ffoZZGY3UPPsZQIEEK5MaiLdVr8A0C0QfBXHrPxBGaF37wXQnpzDVlPgzTW3z/CfoeUxcfcmAh+BqDNKVT5dz9FDh76VhN+tKjO2wT6GuUn4PxbLyZIs7PqcQo9fos8nmdXHysqsLj8CZ8odcnaKR5HArjw5ZCGR47ykKITFmBQ/1DuCxHGvwDwct1hBD/EfV3Poe6yS/r/Tyak4evqMZT4FFuG86V7j4bW59JlDtf6Chv9hisjh/nSzcGk/S7D8mYVsdvU46EQwqe8cDshWSx42F58ZnUINxeNkcVSkSZwnkcQoogLrmQMT/eWHDioQDKFWNT+xEZOMDZkBiFi1Oras1rMXR8eyUcm5Q+sU2Z+oRNceN9GmbAEqCRJv/I76j38SYS9sniD8ZIgu507ioxVow0JlF+sUr3VuDYAiEyMXq+1juB4+x/bAV/KzyuhHE4BAB4TnZw3QzQQthtxGzrPgcPCDwAtNurjeXZQOhziXIbypIsNiX3h1V1fUxRvpsjScMmpgLCFuHh3MSDBMw8yR0Y4lXX6NK10/GqjHstbMhxEAYkHtu53B+03/m9xwnjQd4wSMHLofxHb4IayHrdbyhzo455iAHitvtaktzxiMrdRF+HDBafBbneKM+4rl8qW86CUaTWDMOWIIC7Ttyzqw2aJW/DNqGwxLLShmTOWmab//Kcbc551bb4/iRcYinvkqG2+iyFPwfCderbXt35rJM2ZjQ4KQaJJxzN9a26nYIHKu8zg3e2utAgGx1h5JkHIy0ASl+Ekf4v7Adq8cIOouS89nWvc+Q5P+Iw9PBDijRnW5XPmTdD5W/Kd8HIv4BN19TsdrLrzab3dbzP9lHo8N91mHmlEoisyxxgucC1UrCkxmeP2p+i4TMusUvzQ05k7T5S06aUygvazXuPOUehmQfmFOd/+Ex9vbha4XIZKeKzHUA9/+4fCpQ7HAYMcTa63drnoBybCrGbQtk+XdXcvp0tPK826myNYpAsCeJVlyUj4xXcl6A/SGVcFdLrqyR1yhTBwwChmGPA/0NB4nGcIlHcP9Bc8DjOr618jmMae1fMuaMur0sDqctxXpdaZOoVAwX9lLKoH+u+gMdtQ7Sb4RPIcL7rUBfXwzwoeuovRzP95Lwz5nMdp/GI8TGdXabuzgT+Z9ffBRSYOH6mQXcV7G6E60QZrvesEgAWMTGn8zD9HGln7Te3jzq6xnR6mscD2t+8InbLiH0UEqJTuLIdhbIPweMuROjA/mQyuczv989CeijaZH4fXkm+h1uCS1DueviToON7i1MkTgftl/C7QRcdRd38NQ7zF+LWkm3TftTzCniOIE7IvxHBzZzGVc1PETa7/eJ8Nw6+a5D8DNJtuJx7NsMnAEHeA8jjB4UOtFGNvNcQ58kSDmkHY7kbwWT4w/h08ScIOziTf2yJ+6s5YGcp42+sGvjHlwhxzcWPZ51OVJZh4FuNW5E5F+kczkajfPfxTfib4H1I85mWy0wEz2MIByLMRZlChNjm0MOIT0fIA8RP9DQG5GXE+TvwYwj5M+rrEd+GweFDGCHmuEKiYQDvO+jgYqa5Dvy8tbAxyCGgvQF/L9J4ShevwC4bh3yrOhZ+Hsr8mvnBwxPF6uo63C86Y9DOYvRrFfi4Xf5elMfNn15/FSF/CcBC8ddyXE9nXZ32iuNAtwCVHMC987c4jcE8ifReFAxneFlcmX4l6Ls4nu35cxvQv8o0xBfAtyI9IpuH4yj/BOgNGNAgTiMcwGl4/pXnNUyD49kV9YP/t/Cc94JLQz5LE/OJfRrynoL/A/xb3I9MHk8qe7524XYuR/4H8Afg17plOQ/pN1Dusew6OS5UD4zcEdEaEOaONaOyL4H8Kjo2DuFlkKIZoEc5H2lhgJHm+FDwvJHJ41+Ycye/Ho3ic7lOdyNm7wWo8EGU5RkXMwz+NF5lvg1eVoWrQF8GXw6eGrTFnxXyb443I0+oBtq4D/ljQFsJ3w9x4ZDPV9EMEv+MdgyI96K98fiILAlV2oNB85PV++Bh6RBjhPSUIt4C/pvAsxp1b0b6Unh2YZQPdkYFuCLqql6GLgATP77BwDai8kXwn4OfB3XYhpBnBNeUXasfD5xBa0Qe26p6hLGOjo4mxAVQmTKtmQaY351dJnFZfsnlD+3YsXTkInwCvgWDfIGJoVCoP4LFyFsIEHcgzGM6O9TPALgqwiqXj/xvAoAFoBdi0N9iPjjmccfLK3kuJrMNk3UF+PsBrPXMBBdF2q2vk4L/bsEuQnYElbyGQvsQvp6h8yDZiXLoBM729BHy74V/GA+dMwHwzzFTC9Hw/cyI8nvRKTwqizh/XcL7IPHKC75pIJdj8Nsy+ccQypiUg6j78yh3O37yPwFPTt/helD/a8hnW8Ltuo6Nbxp1XQT+CYhXIYMfV1OIM1jjAHgF4nyxasPzq3QD0gwIvzCnOR/kEvSZxxlAPXxkOtWB8RT7glyh81hRxqHg99CBJMInUVnXb4G5DKeR9zP4GPyD4LkbfhbotyBdD/888yEcDn8E9E3wnwcP27WrEX8cYRT+mQzfKMTZviTAwxIVAc88pNkm1SD+CfTpUoRbkT6EcAZ4GLR8xLnNavgG7rc7JtDHgFYHz79ouIV/IY9wNPwy+GbQH0Bbg5kfLg/paqQd5AnbDJqwaZzfZaOYM9sB1evAwEs2v+7ejHQz4rzcszSxytwAfxk8vsNw+DcvLG3cIvs6pN9GSJC0Q5CKKyA1jyM5B3Rhp1BfG/xDvP1gPrip8FznFvDMQGd3QIK+h45PA99y1LMXcV7uFdTFqv4AeNdgcHngfwSeJeYIJJE/zL8faVav2QhZSrm/j0Ayd4Pm9pvHci88L1I14GvFInYtVPY3qIPLsBMIdsaAFpj+j0cmA8K6ygAI/c7my+Qzj5vPPK7nfZmok2lZcRX2pgi0XJfGIRzX4dbDoWj7DDyiHy5vVlnRBuiifbdcdj2ZPLfu7H67q2Z2P7v679blMqGe8+cwizwAtHnqDj1DZxvz15nL6gbyxUYYIffzjDxZ7L2Ouu2dqaKzAsWdQwH2ruO+dnX2DPkunxv+Pf5zys+0I1BGnCWhy6ECYZxPo3fVe3ofmf90Girr4ueKM/mC2NUQ08GVnf7/+FkQ+F94ypkix+OazQAAAABJRU5ErkJggg==" /> From Yeoman 1.0
Yeoman automatically loads all node_modules prefixed with "grunt" as grunt tasks.  Just install grunt-devserver
and you're ready to go
```
grunt devserver
```

## Version Notes
### 0.3.0
 * added https support [\#2](https://github.com/devpaul/grunt-devserver/issues/2)
 * conformed to the grunt options standard (breaking change)
 * added type parameter

### 0.2.2
 * added cache control option [\#1](https://github.com/devpaul/grunt-devserver/issues/1)

## Future
* serve up multiple folders on a single server
* file configuration with a .devserverrc file
* start multiple servers using a grunt multiconfig or using a file config
* proxy service
* websocket server

## Logos and Tools
Logos and tools are property of their respective owners.
<br> [Grunt](http://www.gruntjs.com)
<br> [Yeoman](http://www.yeoman.io)
